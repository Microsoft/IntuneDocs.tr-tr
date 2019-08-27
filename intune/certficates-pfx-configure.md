---
title: Microsoft Intune-Azure 'da özel ve ortak anahtar sertifikaları kullanma | Microsoft Docs
description: Kök sertifikayı dışarı aktarma, sertifika şablonunu yapılandırma, indirme ve Intune sertifika Bağlayıcısı 'nı (NDES) yükleme adımları da dahil olmak üzere Microsoft Intune ile ortak anahtar şifreleme standartları (PKCS) sertifikaları ekleyin veya oluşturun, cihaz oluşturun yapılandırma profili ve Azure 'da ve sertifika yetkiliniz için bir PKCS sertifika profili oluşturun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0cda32e72956e5998d5ebc8d8bed2baea39951ec
ms.sourcegitcommit: 58a22f1b4a3fffffb1f7da228f470b3b0774fc42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2019
ms.locfileid: "70021812"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve kullanma

Intune, özel ve ortak anahtar çifti (PKCS) sertifikalarının kullanımını destekler. Bu makale, şirket içi sertifika bağlayıcıları gibi gerekli altyapıyı yapılandırmanıza, PKCS sertifikasını dışarı aktarmaya ve sonra sertifikayı bir Intune cihaz yapılandırma profiline eklemenize yardımcı olabilir.

Microsoft Intune, kuruluşların kaynaklarına erişim ve kimlik doğrulama için PKCS sertifikaları kullanmak üzere yerleşik ayarları içerir. Sertifikalar, VPN veya WiFi ağı gibi şirket kaynaklarınıza kimlik doğrular ve erişimi güvenli hale getirin. Bu ayarları Intune 'daki cihaz yapılandırma profillerini kullanarak cihazlara dağıtırsınız.


## <a name="requirements"></a>Gereksinimler

PKCS sertifikalarını Intune ile kullanmak için aşağıdaki altyapıya sahip olmanız gerekir:

- **Active Directory etki alanı**:  
  Bu bölümde listelenen tüm sunucular Active Directory etki alanına katılmalıdır.

  Active Directory Domain Services (AD DS) yükleme ve yapılandırma hakkında daha fazla bilgi için bkz. [AD DS tasarım ve planlama](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Sertifika yetkilisi**:  
   Bir kuruluş sertifika yetkilisi (CA).

  Active Directory Sertifika Hizmetleri 'ni (AD CS) yükleme ve yapılandırma hakkında daha fazla bilgi için bkz. [Active Directory Sertifika Hizmetleri adım adım Kılavuzu](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]  
  > Intune, AD CS'yi, Tek Başına bir CA yerine bir Kurumsal Sertifika Yetkilisi (CA) ile çalıştırmanızı gerektirir.

- **İstemci**:  
  Kurumsal CA 'ya bağlanmak için.

- **Kök sertifika**:  
  Kök sertifikanızın Kurumsal CA'ndan dışa aktarılmış bir kopyası.

- **Microsoft Intune sertifika Bağlayıcısı** ( *NDES sertifika Bağlayıcısı*da denir):  
  Intune portalında **cihaz yapılandırma** > **sertifikası bağlayıcıları** > **Ekle**' ye gidin ve *PKCS #12 bağlayıcısını yüklemek için adımları*izleyin. Sertifika Bağlayıcısı yükleyicisini **Ndesconnectorsetup. exe**' yi indirmeye başlamak için portaldaki indirme bağlantısını kullanın.  

  Intune, her örnek ayrı bir Windows Server üzerinde olmak üzere, kiracı başına bu bağlayıcının en fazla 100 örneğini destekler. Bu bağlayıcının bir örneğini, Microsoft Intune için PFX Sertifika bağlayıcısının bir örneğiyle aynı sunucuya yükleyebilirsiniz. Birden çok bağlayıcı kullandığınızda, kullanılabilir bağlayıcı örnekleri PKCS sertifika isteklerinizi işleyebilmeniz için bağlayıcı altyapısı yüksek kullanılabilirliği ve yük dengelemeyi destekler. 

  Bu bağlayıcı, kimlik doğrulama veya S/MIME e-posta imzalama için kullanılan PKCS sertifika isteklerini işler.

  Microsoft Intune Sertifika Bağlayıcısı Ayrıca federal bilgi Işleme standardı (FIPS) modunu destekler. FIPS gerekli değildir ancak etkinleştirildiğinde sertifika verebilir ve iptal edebilirsiniz.

- **Microsoft Intune Için PFX Sertifika Bağlayıcısı**:  
  S/MIME e-posta şifrelemesini kullanmayı planlıyorsanız, *Içeri AKTARıLAN PFX sertifikalarına*yönelik bağlayıcıyı Indirmek için Intune portalını kullanın.  **Cihaz yapılandırma** > **sertifikası**bağlayıcıları > **Ekle**' ye gidin ve *içeri aktarılan PFX sertifikalarına yönelik bağlayıcı 'yı yüklemek için adımları*izleyin. **Pfxcertificateconnectorbootstrapper. exe**yükleyicisini yüklemeye başlamak için portaldaki indirme bağlantısını kullanın. 

  Her Intune kiracısı, bu bağlayıcının tek bir örneğini destekler. Bu bağlayıcıyı, Microsoft Intune sertifika bağlayıcısının bir örneğiyle aynı sunucuya yükleyebilirsiniz.

  Bu bağlayıcı, belirli bir kullanıcı için S/MIME e-posta şifrelemesi için Intune 'a içeri aktarılan PFX dosyaları isteklerini işler.  

  Bu bağlayıcı, yeni sürümler kullanılabilir hale geldiğinde kendisini otomatik olarak güncelleştirebilir. Güncelleştirme özelliğini kullanmak için şunları yapmanız gerekir:
  - Sunucunuza Microsoft Intune için Içeri aktarılan PFX Sertifika bağlayıcısını yükler.  
  - Önemli güncelleştirmeleri otomatik olarak almak için, bağlayıcının **443**numaralı bağlantı noktasında **AutoUpdate.msappproxy.net** 'e başvurdığına izin veren güvenlik duvarlarının açık olduğundan emin olun.   

  Bağlayıcının erişebilmesi gereken tüm ağ uç noktaları hakkında daha fazla bilgi için bkz. [Microsoft Intune sertifika Bağlayıcısı](intune-endpoints.md#microsoft-intune-certificate-connector).

- **Windows Server**:  
  Barındırmak için bir Windows Server kullanın:

  - Microsoft Intune Sertifika Bağlayıcısı-kimlik doğrulama ve S/MIME e-posta imzalama senaryoları için
  - For S/MIME e-posta şifreleme senaryolarında PFX Sertifika Bağlayıcısı Microsoft Intune.

  Aynı sunucuya hem bağlayıcıları (*Microsoft Intune sertifika Bağlayıcısı* ve *PFX Sertifika Bağlayıcısı*) yükleyebilirsiniz.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Kök sertifikayı Kurumsal CA'dan dışa aktarın

VPN, WiFi veya diğer kaynaklarla bir cihazın kimliğini doğrulamak için bir cihazın kök veya ara CA sertifikası olması gerekir. Aşağıdaki adımlar, Kurumsal CA'nızdan gerekli sertifikayı nasıl alacağınızı açıklar.

**Komut satırı kullanın**:  
1. Kök sertifika yetkilisi sunucusunda yönetici hesabıyla oturum açın.
 
2. Çalıştır 'a gidin ve ardından komut istemi 'ni açmak için **cmd** girin. >  
    
3. Kök sertifikayı *CA_NAME. cer*adlı bir dosya olarak dışarı aktarmak için **certutil-CA. CERT CA_NAME. cer** öğesini belirtin.



## <a name="configure-certificate-templates-on-the-ca"></a>CA 'da sertifika şablonlarını yapılandırma

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. **Sertifika Yetkilisi** konsolunu açın, **Sertifika Şablonları**'na sağ tıklayın ve **Yönet**'i seçin.
3. **Kullanıcı** sertifika şablonunu bulun, şablona sağ tıklayın ve **Şablonu Yinele**’yi seçin. **Yeni Şablon Özellikleri** açılır.

    > [!NOTE]
    > S/MIME e-posta imzalama ve şifreleme senaryolarında, birçok yönetici imzalama ve şifreleme için ayrı sertifikalar kullanır. Microsoft Active Directory Sertifika Hizmetlerini kullanıyorsanız, S/MIME e-posta imzalama sertifikaları için **Yalnızca Exchange İmzası** şablonunu ve S/MIME şifreleme sertifikaları için de **Exchange Kullanıcısı** şablonunu kullanabilirsiniz.  3\. taraf bir sertifika yetkilisi kullanıyorsanız, imzalama ve şifreleme şablonlarını ayarlamaya yönelik kendi kılavuzlarını gözden geçirmeniz önerilir.

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
13. Sunucunun kayıtlı cihazlar ve kullanıcılar için sertifikaları yönetmesi için aşağıdaki adımları kullanın:

    1. Sertifika Yetkilisine sağ tıklayın ve ardından **Özellikler**’i seçin.
    2. Güvenlik sekmesinde, bağlayıcıları (**Microsoft Intune Sertifika Bağlayıcısı** veya **Microsoft Intune için PFX Sertifika Bağlayıcısı**) çalıştırdığınız sunucunun Bilgisayar hesabını ekleyin. 
    3. **Sertifikaları Yayımla ve Yönet** ve **Sertifikaları İste**’ye izin ver, bilgisayar hesabına izin verir.

14. Kurumsal CA'da oturumu kapatın.

## <a name="download-install-and-configure-the-certificate-connectors"></a>Sertifika bağlayıcılarını indirme, yükleme ve yapılandırma

### <a name="microsoft-intune-certificate-connector"></a>Microsoft Intune Sertifika Bağlayıcısı

> [!IMPORTANT]  
> Microsoft Intune Sertifika Bağlayıcısı, veren sertifika yetkilisine (CA) yüklenemez ve bunun yerine ayrı bir Windows Server 'da yüklü olmalıdır.  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **sertifika bağlayıcıları** > **Ekle**' yi seçin.
3. Bağlayıcıyı yükleyeceğiniz sunucudan erişebileceğiniz bir konuma bağlayıcı dosyasını indirin ve kaydedin.

    ![Microsoft Intune Sertifika Bağlayıcısı indir](media/certificates-pfx-configure/download-ndes-connector.png)
 

4. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. NDES Sertifika bağlayıcısının gerektirdiği .NET 4.5 Framework veya sonraki bir sürümünün yüklü olduğundan emin olun. .NET 4.5 Framework, Windows Server 2012 R2 ve daha yeni sürümlere otomatik olarak eklenir.
    2. Yükleyiciyi (NDESConnectorSetup.exe) çalıştırın ve varsayılan konumu kabul edin. Bağlayıcı `\Program Files\Microsoft Intune\NDESConnectorUI` konumuna yüklenir. Yükleyici Seçenekleri’nde **PFX Dağıtımı**’nı seçin. Devam edin ve yüklemeyi tamamlayın.
    3. Varsayılan olarak, bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet’e erişmek için bir ara sunucu gerekiyorsa, yerel hizmet hesabının sunucudaki ara sunucu ayarlarına erişebildiğinizden emin olun.

5. Microsoft Intune Sertifika Bağlayıcısı **kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**’ı seçin ve yönetim izinleri olan bir hesap girin.
6. **Gelişmiş** sekmesinde **Bu bilgisayarın SİSTEM hesabını kullan (varsayılan)** ’ı seçili bırakmanız önerilir.
7. **Uygula** > **Kapat**
8. Intune portalına geri dönün (**Intune** > **cihaz yapılandırması** > **sertifika bağlayıcıları**). Birkaç dakika sonra yeşil bir onay işareti gösterilir ve **bağlantı durumu** **etkin**olur. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.
9. Ağ ortamınızda bir Web proxy 'niz varsa, bağlayıcının çalışmasını sağlamak için ek yapılandırmalara ihtiyacınız olabilir. Daha fazla bilgi için, bkz. Azure Active Directory belgelerinde [mevcut şirket içi proxy sunucularıyla çalışma](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) .

> [!NOTE]  
> Microsoft Intune Sertifika Bağlayıcısı TLS 1,2 ' i destekler. Bağlayıcıyı barındıran sunucuda TLS 1,2 yüklüyse, bağlayıcı TLS 1,2 ' yi kullanır. Aksi halde TLS 1,1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>Microsoft Intune için PFX Sertifika Bağlayıcısı

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **sertifika bağlayıcıları** > **Ekle** öğesini seçin
3. Microsoft Intune için PFX Sertifika Bağlayıcısı’nı indirin ve kaydedin. Bağlayıcıyı, yükleyeceğiniz sunucudan erişilebilir bir konuma kaydedin.
4. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. Microsoft Intune için PFX Sertifika Bağlayıcısı'nın gerektirdiği .NET 4.6 Framework veya sonraki bir sürümünün yüklü olduğundan emin olun. .NET 4.6 Framework yüklü değilse yükleyici bunu otomatik olarak yükler.
    2. Yükleyiciyi (PfxCertificateConnectorBootstrapper. exe) çalıştırın ve bağlayıcıyı `Program Files\Microsoft Intune\PFXCertificateConnector`yükleyecek olan varsayılan konumu kabul edin.
    3. Bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet erişimi için bir ara sunucu gerekiyorsa, yerel hizmet hesabının sunucudaki ara sunucu ayarlarına erişebildiğinizden emin olun.

5. Microsoft Intune için PFX Sertifika Bağlayıcısı yüklendikten sonra **Kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**'ı seçin ve Azure genel yöneticisi veya Intune yöneticisi izinleri olan bir hesap girin.
6. Pencereyi kapatın.
7. Azure Portal (**Intune** > **cihaz yapılandırması** > **sertifika bağlayıcıları**) bölümüne geri dönün. Birkaç dakika sonra yeşil bir onay işareti gösterilir ve **bağlantı durumu** **etkin**olur. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.

## <a name="create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.
    ![Intune 'a gidin ve güvenilen bir sertifika için yeni bir profil oluşturun](media/certificates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

3. **Ayarlar**'a gidin ve daha önce içeri aktarmış olduğunuz .cer dosyası Kök CA Sertifikası'nı girin.

   > [!NOTE]
   > **2. adımda**seçtiğiniz platforma bağlı olarak, sertifika için **Hedef depoyu** seçme seçeneğiniz olabilir veya olmayabilir.

   ![Bir profil oluşturun ve güvenilen bir sertifikayı karşıya yükleyin](media/certificates-pfx-configure/certificates-pfx-configure-profile-fill.png) 

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

    - **Yenileme eşiği (%)** : Önerilen% 20 ' dir.
    - **Sertifika geçerlilik süresi**: Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanmış olabilir.
    - **Anahtar depolama sağlayıcısı (KSP)** : Windows için, cihazdaki anahtarların depolanacağı yeri seçin.
    - **Sertifika yetkilisi**: Kuruluş sertifika yetkilinizin iç tam etki alanı adını (FQDN) görüntüler.
    - **Sertifika yetkilisi adı**: Kuruluş SERTIFIKA yetkilinizin adını (örneğin, "contoso sertifika yetkilisi") listeler.
    - **Sertifika şablonu adı**: Daha önce oluşturulan şablonun adı. **Şablon adı**’nın varsayılan olarak **Şablon görüntü adı** ile *boşluksuz* aynı olduğunu unutmayın.
    - **Konu adı biçimi**: Aksi belirtilmedikçe bu seçeneği **ortak ad** olarak ayarlayın.
    - **Konu diğer adı**: Aksi belirtilmedikçe, bu seçeneği **Kullanıcı asıl adı (UPN)** olarak ayarlayın.

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

   > [!NOTE]
   > Android kurumsal profiline sahip cihazlarda, PKCS sertifika profili kullanılarak yüklenen sertifikalar cihazda görünmez. Başarılı sertifika dağıtımını onaylamak için, Intune konsolundaki profilin durumunu denetleyin.

## <a name="create-a-pkcs-imported-certificate-profile"></a>PKCS içeri aktarılmış sertifika profili oluşturma

Belirli bir kullanıcıya daha önce verilen sertifikaları, içindeki herhangi bir CA 'dan Intune 'a aktarabilirsiniz. İçeri aktarılan sertifikalar, kullanıcının kaydettiği her cihaza yüklenir. S/MIME e-posta şifreleme, var olan PFX sertifikalarını Intune’a aktarmak için en yaygın kullanılan senaryodur. Bir kullanıcının e-postayı şifrelemek için çok sayıda sertifikası olabilir. Daha önce şifrelenmiş olan e-postaların şifrelerini çözmek için kullanıcının tüm cihazlarında bu sertifikaların özel anahtarları bulunmalıdır.

Intune’a sertifika aktarmak için [GitHub’da sağlanan PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanabilirsiniz.

Sertifikaları Intune’da içeri aktardıktan sonra bir **PKCS içeri aktarılmış sertifikası** profili oluşturun ve bu profili Azure Active Directory gruplarına atayın.

1. [Azure portalında](https://portal.azure.com) **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.
2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil Türü**’nü **PKCS içeri aktarılan sertifikası** olarak ayarlayın

3. **Ayarlar**'a gidin ve aşağıdaki özellikleri girin:

    - **Amaçlanan amaç**: Bu profil için içeri aktarılan sertifikaların amaçlanan amacı. Yöneticinin, farklı amaçlara (kimlik doğrulaması, S/MIME imzalaması veya S/MIME şifrelemesi gibi) yönelik içeri aktarılmış sertifikaları olabilir. Sertifika profilinde seçilen kullanım amacı, sertifika profilini doğru içeri aktarılmış sertifikalarla eşleştirir.
    - **Sertifika geçerlilik süresi**: Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanmış olabilir.
    - **Anahtar depolama sağlayıcısı (KSP)** : Windows için, cihazdaki anahtarların depolanacağı yeri seçin.

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="whats-new-for-connectors"></a>Bağlayıcılar yenilikleri
İki sertifika Bağlayıcısı için güncelleştirmeler düzenli aralıklarla yayımlanır. Bir bağlayıcıyı güncelleştirdiğimiz zaman, buradaki değişiklikler hakkında bilgi edinebilirsiniz. 

*Microsoft Intune Için PFX sertifikaları Bağlayıcısı* , *Intune sertifika Bağlayıcısı* el ile güncelleştirilirken [otomatik güncelleştirmeleri destekler](#requirements).

### <a name="may-17-2019"></a>17 Mayıs 2019  
- **Microsoft Intune-sürüm 6.1905.0.404 için PFX sertifikaları Bağlayıcısı**  
  Bu sürümdeki değişiklikler:  
  - Mevcut PFX sertifikalarının yeniden işlenmesine devam edildiği bir sorun düzeltildi ve bu, bağlayıcının yeni istekleri işlemeyi durdurmasına neden oluyor. 

### <a name="may-6-2019"></a>6 Mayıs 2019  
- **Microsoft Intune-sürüm 6.1905.0.402 için PFX sertifikaları Bağlayıcısı**  
  Bu sürümdeki değişiklikler:  
  - Bağlayıcının yoklama aralığı 5 dakikadan 30 saniyeye düşürülür.
 
### <a name="april-2-2019"></a>2 Nisan 2019  
- **Intune sertifika Bağlayıcısı-sürüm 6.1904.1.0**  
  Bu sürümdeki değişiklikler:  
  - Bağlayıcının bir genel yönetici hesabıyla oturum açtıktan sonra Intune 'a kaydolmasına neden olabilecek bir sorun düzeltildi.  
  - Sertifika iptalinde güvenilirlik düzeltmeleri içerir.  
  - PKCS sertifika isteklerinin işlenme hızını artırmak için performans düzeltmelerini içerir.  

- **Microsoft Intune-sürüm 6.1904.0.401 için PFX sertifikaları Bağlayıcısı**
  > [!NOTE]  
  > PFX bağlayıcısının bu sürümü için otomatik güncelleştirme, 11 Nisan 2019 tarihine kadar kullanılabilir değildir.  

  Bu sürümdeki değişiklikler:  
  - Bağlayıcının bir genel yönetici hesabıyla oturum açtıktan sonra Intune 'a kaydolmasına neden olabilecek bir sorun düzeltildi.  


## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[SCEP sertifikaları kullanın](certificates-scep-configure.md)veya [bir DIGICERT PKI Manager Web hizmetinden PKCS sertifikaları verin](certificates-digicert-configure.md).


