---
title: Microsoft Intune-Azure 'da içeri aktarılan PFX sertifikalarını kullanma | Microsoft Docs
description: Sertifikaları içeri aktarma, sertifika şablonunu yapılandırma, Intune Içeri aktarılan PFX Sertifika bağlayıcısının yüklenmesi ve Içeri aktarılan bir PKCS oluşturma dahil olmak üzere Microsoft Intune ile içeri aktarılan ortak anahtar şifreleme standartları (PKCS) sertifikalarını kullanın Sertifika profili.
keywords: ''
author: ralms
ms.author: brenduns
manager: dougeby
ms.date: 09/16/2019
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
ms.openlocfilehash: b801da3bd4245361e8c55a40c67daf2c8890fd1e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729389"
---
# <a name="configure-and-use-imported-pkcs-certificates-with-intune"></a>Intune ile içeri aktarılan PKCS sertifikalarını yapılandırma ve kullanma

Microsoft Intune, genellikle e-posta profilleriyle S/MIME şifrelemesi için kullanılan içeri aktarılan ortak anahtar çifti (PKCS) sertifikalarının kullanımını destekler. Intune 'daki belirli e-posta profilleri, s/MIME imzalama sertifikası ve S/MIME şifreleme sertifikası tanımlayabileceğiniz S/MIME 'yi etkinleştirme seçeneğini destekler.

E-posta belirli bir sertifikayla şifrelendiğinden, S/MIME şifrelemesi zordur. Şifresinin çözülmesi için e-postayı okuduğunuz cihazda e-postayı şifreleyen sertifikanın özel anahtarına sahip olmanız gerekir. Şifreleme sertifikaları düzenli olarak yenilenir, yani eski e-postayı okuyabilmeniz için tüm cihazlarınızda şifreleme geçmişinize ihtiyacınız olabilir.  Aynı sertifikanın cihazlarda kullanılması gerektiğinden, bu sertifika teslim mekanizmaları cihaz başına benzersiz sertifikalar sunduğundan bu amaçla [SCEP](certificates-scep-configure.md) veya [PKCS](certficates-pfx-configure.md) sertifika profillerini kullanmak mümkün değildir. 

Intune ile S/MIME kullanma hakkında daha fazla bilgi için, [e-postayı şifrelemek üzere s/MIME kullanın](certificates-s-mime-encryption-sign.md).

## <a name="requirements"></a>Gereksinimler

İçeri aktarılmış PKCS sertifikalarını Intune ile kullanmak için aşağıdaki altyapıya sahip olmanız gerekir:

- **Microsoft Intune Için PFX Sertifika Bağlayıcısı**:  
  Her Intune kiracısı, bu bağlayıcının tek bir örneğini destekler. Bu bağlayıcıyı, Microsoft Intune sertifika bağlayıcısının bir örneğiyle aynı sunucuya yükleyebilirsiniz.

  Bu bağlayıcı, belirli bir kullanıcı için S/MIME e-posta şifrelemesi için Intune 'a içeri aktarılan PFX dosyaları isteklerini işler.  

  Bu bağlayıcı, yeni sürümler kullanılabilir hale geldiğinde kendisini otomatik olarak güncelleştirebilir. Güncelleştirme özelliğini kullanmak için, bağlayıcının **443**numaralı bağlantı noktasında **AutoUpdate.msappproxy.net** ile iletişim kurabildiğinden emin olmanız gerekir.  

  Bağlayıcının eriştiği tüm ağ uç noktaları hakkında daha fazla bilgi için bkz. [Intune ağ yapılandırma gereksinimleri ve bant genişliği](../fundamentals/network-bandwidth-use.md).


- **Windows Server**:  
  Microsoft Intune için PFX Sertifika bağlayıcısını barındırmak üzere bir Windows Server kullanın.  Bağlayıcı, Intune 'a içeri aktarılan sertifikalara yönelik istekleri işlemek için kullanılır.

  Intune, *Microsoft Intune Için PFX Sertifika Bağlayıcısı*ile aynı sunucuya *Microsoft Intune sertifika Bağlayıcısı* yüklenmesini destekler.

  Bağlayıcıyı desteklemek için, sunucunun .NET 4,6 Framework veya üstünü çalıştırması gerekir. Bağlayıcıyı yüklemeye başladığınızda .NET 4,6 çerçevesi yüklenmemişse, bağlayıcı yüklemesi otomatik olarak yüklenir.

- **Visual studio 2015 veya üzeri** (isteğe bağlı): PFX sertifikalarını Microsoft Intune içeri aktarmaya yönelik cmdlet 'lerle birlikte yardımcı PowerShell modülünü oluşturmak Için Visual Studio 'yu kullanırsınız. Yardımcı PowerShell cmdlet 'lerini almak için bkz. [GitHub 'Da Pfxımport PowerShell projesi](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

## <a name="how-it-works"></a>Nasıl çalıştığı

Bir kullanıcıya **içeri aktarılan BIR PFX sertifikasını** dağıtmak için Intune 'u kullandığınızda, cihaza ek olarak iki bileşen oynatılır: 

- **Intune hizmeti**: PFX sertifikalarını şifreli bir durumda depolar ve sertifikanın Kullanıcı cihazına dağıtımını işler.  Sertifikaların özel anahtarlarını koruyan parolalar, Intune 'un özel anahtara herhangi bir zamanda erişemeyeceğinden emin olmak için bir donanım güvenlik modülü (HSM) veya Windows şifrelemesi kullanılarak karşıya yüklenmeden önce şifrelenir.
- **Microsoft Intune Için PFX Sertifika Bağlayıcısı**: bir cihaz Intune 'a AKTARıLMıŞ bir PFX sertifikası istediğinde, şifreli parola, sertifika ve cihazın ortak anahtarı bağlayıcıya gönderilir.  Bağlayıcı, şirket içi özel anahtarı kullanarak parolanın şifresini çözer ve sertifikayı Intune 'a geri göndermeden önce, parolayı (ve iOS kullanılıyorsa tüm plist profillerini) cihaz anahtarıyla yeniden şifreler.  Intune daha sonra sertifikayı cihaza gönderir ve cihaz cihazın özel anahtarıyla şifresini çözebilir ve sertifikayı yükler.

## <a name="download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune"></a>Microsoft Intune için PFX Sertifika bağlayıcısını indirin, yükleyin ve yapılandırın

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) portalında **cihaz yapılandırma** > **sertifika bağlayıcıları** > **Ekle** ' yi seçin.

   ![Microsoft Intune indirmek için PFX Sertifika Bağlayıcısı](./media/certificates-imported-pfx-configure/download-imported-pfxconnector.png)

2. *Microsoft Intune Için PFX Sertifika bağlayıcısını* , bağlayıcıyı yükleyeceğiniz sunucudan erişilebilen bir konuma indirmek için yönergeleri izleyin.
3. İndirme tamamlandıktan sonra, sunucusunda oturum açın ve yükleyiciyi (PfxCertificateConnectorBootstrapper. exe) çalıştırın.  
   - Varsayılan yükleme konumunu kabul ettiğinizde, bağlayıcı `Program Files\Microsoft Intune\PFXCertificateConnector` ' a yüklenir.
   - Bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet erişimi için bir proxy gerekliyse, yerel hizmet hesabının sunucudaki proxy ayarlarına erişediğini doğrulayın.

4. Microsoft Intune için PFX Sertifika Bağlayıcısı yüklendikten sonra **Kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**'ı seçin ve Azure genel yöneticisi veya Intune yöneticisi izinleri olan bir hesap girin.

   > [!WARNING]
   > Varsayılan olarak, Windows Server **IE artırılmış güvenlik yapılandırması** **Açık** olarak ayarlanır ve bu, Office 365 ' de oturum açma sorunları oluşmasına neden olabilir.

5. Pencereyi kapatın.
6. Intune portalında, **cihaz yapılandırması** > **sertifika bağlayıcıları**' na geri dönün. Birkaç dakika içinde yeşil bir onay işareti görünür ve **bağlantı durumu** **etkin**olur. Bağlayıcı sunucusu artık Intune ile iletişim kurabilir.

## <a name="import-pfx-certificates-to-intune"></a>PFX sertifikalarını Intune 'a aktarma

Kullanıcılarınızın PFX sertifikalarını Intune 'a aktarmak için [Microsoft Graph](https://docs.microsoft.com/graph) kullanırsınız. GitHub 'da yardımcı [Pfxiçeri aktarma PowerShell projesi](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell) , işlemleri kolay bir şekilde yapmak için cmdlet 'ler sağlar.

Graph kullanarak kendi özel çözümünüzü kullanmayı tercih ediyorsanız, [Userpfxsertifikası kaynak türünü](https://docs.microsoft.com/graph/api/resources/intune-raimportcerts-userpfxcertificate?view=graph-rest-beta)kullanın.

### <a name="build-pfximport-powershell-project-cmdlets"></a>Derleme ' Pfxımport PowerShell projesi ' cmdlet 'leri

PowerShell cmdlet 'lerini kullanmak için, Visual Studio kullanarak projeyi kendiniz derleyebilirsiniz. İşlem düz bir işlemdir ve sunucuda çalıştırılabileceği sürece, iş istasyonunuzda çalıştırmanızı öneririz.  

1. GitHub 'daki [Intune-kaynak erişimi](https://github.com/microsoft/Intune-Resource-Access) deposunun köküne gidin ve sonra da depoyu makinenize git ile indirin veya kopyalayın.

   ![GitHub indirme düğmesi](./media/certificates-imported-pfx-configure/github-download.png)

2. @No__t-0 ' a gidin ve Visual Studio ile projeyi, **Pfxımportps. sln**dosyasını kullanarak açın.
3. Üstteki sayfada **hata ayıklamanın** **sürümüne**geçin.
4. **Derleme** bölümüne gidin ve **derleme pfxımportps**' yi seçin. Birkaç dakika sonra Visual Studio 'nun sol alt kısmında bulunan **Derleme başarılı** onay onayını görürsünüz.

   ![Visual Studio derleme seçeneği](./media/certificates-imported-pfx-configure/vs-build-release.png)

5. Yapı işlemi `.\Intune-Resource-Access-develop\src\PFXImportPowershell\PFXImportPS\bin\Release` ' da PowerShell modülüyle yeni bir klasör oluşturur.

   Bu **Sürüm** klasörünü sonraki adımlar için kullanacaksınız.

### <a name="create-the-encryption-public-key"></a>Şifreleme ortak anahtarını oluşturma

PFX sertifikalarını ve özel anahtarlarını Intune 'a içeri aktarırsınız. Özel anahtarı koruyan parola, şirket içinde depolanan bir ortak anahtarla şifrelenir. Ortak/özel anahtar çiftlerini oluşturmak ve depolamak için Windows şifrelemesi, bir donanım güvenlik modülü ya da başka bir şifreleme türü kullanabilirsiniz.  Kullanılan şifrelemenin türüne bağlı olarak, ortak/özel anahtar çifti, yedekleme amacıyla bir dosya biçiminde aktarılabilir.

PowerShell modülü, Windows şifrelemesi kullanarak bir anahtar oluşturmak için yöntemler sağlar. Ayrıca, bir anahtar oluşturmak için diğer araçları da kullanabilirsiniz.  

#### <a name="to-create-the-encryption-key-using-windows-cryptography"></a>Windows şifrelemesi kullanarak şifreleme anahtarını oluşturmak için

1. Visual Studio tarafından oluşturulan *Sürüm* klasörünü **Microsoft Intune Için PFX Sertifika bağlayıcısını**yüklediğiniz sunucuya kopyalayın. Bu klasör PowerShell modülünü içerir.  
2. Sunucusunda, *PowerShell* 'i yönetici olarak açın ve ardından PowerShell modülünü içeren *yayın* klasörüne gidin.
3. Modülü içeri aktarmak için, modülünü içeri aktarmak üzere `Import-Module .\IntunePfxImport.psd1` ' ı çalıştırın.
4. Sonra, @no__t Çalıştır-0

   > [!TIP]  
   > PFX sertifikalarını içeri aktardığınızda kullandığınız sağlayıcının yeniden seçilmesi gerekir. Farklı bir sağlayıcı kullanılması desteklenmekle birlikte, **Microsoft yazılım anahtarı depolama sağlayıcısını**kullanabilirsiniz. Anahtar adı da örnek olarak sağlanır ve tercih ettiğiniz farklı bir anahtar adı kullanabilirsiniz.  

   Sertifikayı iş istasyonunuzdan içeri aktarmayı planlıyorsanız, bu anahtarı aşağıdaki komutla bir dosyaya dışarı aktarabilirsiniz: `Export-IntunePublicKey -ProviderName "<ProviderName>" -KeyName "<KeyName>" -FilePath "<File path to write to>"`

   Özel anahtar, içeri aktarılan PFX sertifikalarının başarıyla işlenebilmesi için, Microsoft Intune için PFX Sertifika bağlayıcısını barındıran sunucuda içeri aktarılmalıdır.  

#### <a name="to-use-a-hardware-security-module-hsm"></a>Donanım güvenlik modülünü (HSM) kullanmak için  

Ortak/özel anahtar çiftini oluşturmak ve depolamak için bir donanım güvenlik modülü (HSM) kullanabilirsiniz. Daha fazla bilgi için bkz. HSM sağlayıcısının belgeleri.

### <a name="import-pfx-certificates"></a>PFX sertifikalarını içeri aktar 

Aşağıdaki işlem, PFX sertifikalarının nasıl içeri aktarılacağını gösteren bir örnek olarak PowerShell cmdlet 'lerini kullanır. Gereksinimlerinize bağlı olarak farklı seçenekler seçebilirsiniz.

Şu seçenekler mevcuttur:  
- Amaçlanan amaç (bir etiketi temel alarak sertifikaları gruplandırır):  
  - atanmadı
  - SMIME şifreleme
  - SMIME imzalama


- Doldurma şeması:  
  - pkcs1
  - oaepSha1
  - oaepSha256
  - oaepSha384
  - oaepSha512

Anahtarı oluşturmak için kullandığınız sağlayıcıyla eşleşen anahtar depolama sağlayıcısını seçin.

#### <a name="to-import-the-pfx-certificate"></a>PFX sertifikasını içeri aktarmak için  

1. Sağlayıcıdan alınan belgeleri izleyerek herhangi bir sertifika yetkilisinden (CA) sertifikaları dışarı aktarın.  Microsoft Active Directory Sertifika Hizmetleri için [Bu örnek komut dosyasını](https://gallery.technet.microsoft.com/Export-CMPfxCertificatesFro-d55f687b)kullanabilirsiniz.   
2. Sunucusunda, *PowerShell* 'i yönetici olarak açın ve ardından PowerShell modülünü içeren *yayın* klasörüne gidin.
3. Modülü içeri aktarmak için @no__t çalıştırın-0  
4. Intune grafiğinde kimlik doğrulaması yapmak için @no__t çalıştırın-0

   > [!NOTE]
   > Kimlik doğrulaması, grafiğe karşı çalıştırıldığı için, AppID için izinler sağlamalısınız. Bu yardımcı programı ilk kez kullandıysanız, *genel yönetici* gerekir. PowerShell cmdlet 'leri [PowerShell Intune örnekleri](https://github.com/microsoftgraph/powershell-intune-samples)ile birlikte kullanılan AppID 'yi kullanır.   
5. İçeri aktardığınız her PFX dosyası için parolayı, `$SecureFilePassword = ConvertTo-SecureString -String "<PFXPassword>" -AsPlainText -Force` çalıştırarak güvenli bir dizeye dönüştürün.  
6. **Userpfxsertifika** nesnesi oluşturmak için `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>"` ' i çalıştırın

   Örneğin: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "C:\temp\userA.pfx" $SecureFilePassword "userA@contoso.com" "Microsoft Software Key Storage Provider" "PFXEncryptionKey" "smimeEncryption" "pkcs1"`

   > [!NOTE]  
   > Sertifikayı bağlayıcının yüklü olduğu sunucudan başka bir sistemden içeri aktardığınızda, Use anahtar dosya yolunu içeren aşağıdaki komutu kullanmalıdır: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>" "<File path to public key file>"`

7. @No__t-1 ' i çalıştırarak **Userpfxsertifikası** nesnesini Intune 'a aktarın

8. Sertifikanın içeri aktarıldığını doğrulamak için @no__t çalıştırın-0

Kullanılabilir diğer komutlar hakkında daha fazla bilgi için, [GitHub 'da, Pfxımport PowerShell projesinde](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell)bulunan Benioku dosyasına bakın.

## <a name="create-a-pkcs-imported-certificate-profile"></a>PKCS içeri aktarılmış sertifika profili oluşturma

Sertifikaları Intune’da içeri aktardıktan sonra bir **PKCS içeri aktarılmış sertifikası** profili oluşturun ve bu profili Azure Active Directory gruplarına atayın.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) portalında **cihaz yapılandırması**@no__t **-2**profil  > **Profil oluştur**' a gidin.
2. Aşağıdaki özellikleri girin:

   - Profil için **Ad**
   - İsteğe bağlı olarak bir açıklama ayarlayın
   - Profili dağıtmak için **Platform**
   - **Profil Türü**’nü **PKCS içeri aktarılan sertifikası** olarak ayarlayın

3. **Ayarlar**'a gidin ve aşağıdaki özellikleri girin:

   - **Amaçlanan amaç**: Bu profil için içeri aktarılan sertifikaların amaçlanan amacını belirtin. Yöneticiler, sertifikaları farklı amaçlanan amaçlarla (kimlik doğrulama, S/MIME imzalama veya S/MIME Şifrelemesi gibi) içeri aktarabilir. Sertifika profilinde seçilen kullanım amacı, sertifika profilini doğru içeri aktarılmış sertifikalarla eşleştirir. Amaçlanan amaç, içeri aktarılan sertifikaları gruplamak için bir etikettir ve bu etiketle içeri aktarılan sertifikaların amaçlanan amacı karşıladığını garanti etmez.  
   - **Sertifika geçerlilik süresi**: geçerlilik süresi sertifika şablonunda değiştirilmediği takdirde, bu seçenek varsayılan olarak bir yıl olur.  
   - **Anahtar depolama sağlayıcısı (KSP)** : Windows için, cihazdaki anahtarları nereye depolayacağınızı seçin.  

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](../configuration/device-profile-assign.md).



