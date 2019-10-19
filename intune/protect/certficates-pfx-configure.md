---
title: Microsoft Intune-Azure 'da özel ve ortak anahtar sertifikaları kullanma | Microsoft Docs
description: Microsoft Intune ile ortak anahtar şifreleme standartları (PKCS) sertifikaları kullanın. Bu, kök sertifikalar ve sertifika şablonları ile çalışmayı, Intune sertifika Bağlayıcısı 'nı (NDES) ve bir PKCS sertifikası için cihaz yapılandırma profillerini yüklemeyi içerir.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f3f4a8c9be4e22f3bc64288a6e3d2ec708186de6
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585197"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve kullanma

Intune, özel ve ortak anahtar çifti (PKCS) sertifikalarının kullanımını destekler. Bu makale, şirket içi sertifika bağlayıcıları gibi gerekli altyapıyı yapılandırmanıza, PKCS sertifikasını dışarı aktarmaya ve sonra sertifikayı bir Intune cihaz yapılandırma profiline eklemenize yardımcı olabilir.

Microsoft Intune, kuruluşların kaynaklarına erişim ve kimlik doğrulama için PKCS sertifikaları kullanmak üzere yerleşik ayarları içerir. Sertifikalar, VPN veya WiFi ağı gibi şirket kaynaklarınıza kimlik doğrular ve erişimi güvenli hale getirin. Bu ayarları Intune 'daki cihaz yapılandırma profillerini kullanarak cihazlara dağıtırsınız.

İçeri aktarılan PKCS sertifikalarını kullanma hakkında daha fazla bilgi için bkz. [Içeri AKTARıLMıŞ PFX sertifikaları](certificates-imported-pfx-configure.md).


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
  Intune portalında, **cihaz yapılandırması** > **sertifika bağlayıcıları** > **Ekle**' ye gidin ve *PKCS #12 bağlayıcısını yüklemek için adımları*izleyin. Sertifika Bağlayıcısı yükleyicisini **Ndesconnectorsetup. exe**' yi indirmeye başlamak için portaldaki indirme bağlantısını kullanın.  

  Intune, kiracı başına bu bağlayıcının en fazla 100 örneğini destekler. Her bir Bağlayıcısı örneği ayrı bir Windows Server üzerinde olmalıdır. Bu bağlayıcının bir örneğini, Microsoft Intune için PFX Sertifika bağlayıcısının bir örneğiyle aynı sunucuya yükleyebilirsiniz. Birden çok bağlayıcı kullandığınızda bağlayıcı altyapısı, kullanılabilir bağlayıcı örnekleri PKCS sertifika isteklerinizi işleyebilmeniz için yüksek kullanılabilirlik ve yük dengelemeyi destekler. 

  Bu bağlayıcı, kimlik doğrulama veya S/MIME e-posta imzalama için kullanılan PKCS sertifika isteklerini işler.

  Microsoft Intune Sertifika Bağlayıcısı Ayrıca federal bilgi Işleme standardı (FIPS) modunu destekler. FIPS gerekli değildir ancak etkinleştirildiğinde sertifika verebilir ve iptal edebilirsiniz.

- **Microsoft Intune Için PFX Sertifika Bağlayıcısı**:  
  S/MIME e-posta şifrelemesini kullanmayı planlıyorsanız, PFX sertifikalarının içeri aktarımını destekleyen *PFX Sertifika bağlayıcısını* Indirmek için Intune portalını kullanın.  **Cihaz yapılandırması** > **sertifika bağlayıcıları** **Ekle**' ye gidin ve *içeri aktarılan PFX sertifikaları için bağlayıcı 'yı yüklemek için adımları*izleyin. **Pfxcertificateconnectorbootstrapper. exe**yükleyicisini yüklemeye başlamak için portaldaki indirme bağlantısını kullanın. 

  Her Intune kiracısı, bu bağlayıcının tek bir örneğini destekler. Bu bağlayıcıyı, Microsoft Intune sertifika bağlayıcısının bir örneğiyle aynı sunucuya yükleyebilirsiniz.

  Bu bağlayıcı, belirli bir kullanıcı için S/MIME e-posta şifrelemesi için Intune 'a içeri aktarılan PFX dosyaları isteklerini işler.  

  Bu bağlayıcı, yeni sürümler kullanılabilir hale geldiğinde kendisini otomatik olarak güncelleştirebilir. Güncelleştirme özelliğini kullanmak için şunları yapmanız gerekir:
  - Sunucunuza Microsoft Intune için PFX Sertifika bağlayıcısını yükler.  
  - Önemli güncelleştirmeleri otomatik olarak almak için, bağlayıcının **443**numaralı bağlantı noktasında **AutoUpdate.msappproxy.net** 'e başvurdığına izin veren güvenlik duvarlarının açık olduğundan emin olun.   

  Intune ve bağlayıcının erişimi olan ağ uç noktaları hakkında daha fazla bilgi için bkz. [Microsoft Intune Için ağ uç noktaları](../fundamentals/intune-endpoints.md).

- **Windows Server**:  
  Barındırmak için bir Windows Server kullanın:

  - Microsoft Intune Sertifika Bağlayıcısı-kimlik doğrulama ve S/MIME e-posta imzalama senaryoları için
  - For S/MIME e-posta şifreleme senaryolarında PFX Sertifika Bağlayıcısı Microsoft Intune.

  Intune, *PFX Sertifika bağlayıcısının* *Microsoft Intune sertifika Bağlayıcısı*aynı sunucuya yüklenmesini destekler.
  
## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Kök sertifikayı Kurumsal CA'dan dışa aktarın

VPN, WiFi veya diğer kaynaklarla bir cihazın kimliğini doğrulamak için bir cihazın kök veya ara CA sertifikası olması gerekir. Aşağıdaki adımlar, Kurumsal CA'nızdan gerekli sertifikayı nasıl alacağınızı açıklar.

**Komut satırı kullanın**:  
1. Kök sertifika yetkilisi sunucusunda yönetici hesabıyla oturum açın.
 
2. **Başlat**  > **Çalıştır**' a gidin ve ardından komut Istemi 'ni açmak için **cmd** yazın. 
    
3. Kök sertifikayı *CA_NAME. cer*adlı bir dosya olarak dışarı aktarmak için **certutil-CA. CERT CA_NAME. cer** öğesini belirtin.



## <a name="configure-certificate-templates-on-the-ca"></a>CA 'da sertifika şablonlarını yapılandırma

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. **Sertifika Yetkilisi** konsolunu açın, **Sertifika Şablonları**'na sağ tıklayın ve **Yönet**'i seçin.
3. **Kullanıcı** sertifika şablonunu bulun, sağ tıklayın ve **Yinelenen şablon** ' u seçerek **yeni şablonun özelliklerini**açın.

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

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Microsoft Intune Sertifika Bağlayıcısı indirme, yükleme ve yapılandırma

> [!IMPORTANT]  
> Microsoft Intune Sertifika Bağlayıcısı, veren sertifika yetkilisine (CA) yüklenemez ve bunun yerine ayrı bir Windows Server 'da yüklü olmalıdır.  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Ekle** >  **cihaz yapılandırması**  > **sertifika bağlayıcıları** ' nı seçin.
3. Bağlayıcıyı yükleyeceğiniz sunucudan erişebileceğiniz bir konuma bağlayıcı dosyasını indirin ve kaydedin.

    ![Microsoft Intune Sertifika Bağlayıcısı indir](./media/certficates-pfx-configure/download-ndes-connector.png)
 

4. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. NDES Sertifika bağlayıcısının gerektirdiği .NET 4.5 Framework veya sonraki bir sürümünün yüklü olduğundan emin olun. .NET 4.5 Framework, Windows Server 2012 R2 ve daha yeni sürümlere otomatik olarak eklenir.
    2. Yükleyiciyi (NDESConnectorSetup.exe) çalıştırın ve varsayılan konumu kabul edin. Bağlayıcı `\Program Files\Microsoft Intune\NDESConnectorUI` konumuna yüklenir. Yükleyici Seçenekleri’nde **PFX Dağıtımı**’nı seçin. Devam edin ve yüklemeyi tamamlayın.
    3. Varsayılan olarak, bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet’e erişmek için bir ara sunucu gerekiyorsa, yerel hizmet hesabının sunucudaki ara sunucu ayarlarına erişebildiğinizden emin olun.

5. Microsoft Intune Sertifika Bağlayıcısı **kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **oturum açın**ve genel yönetici izinlerine sahip bir hesap girin.
6. **Gelişmiş** sekmesinde **Bu bilgisayarın SİSTEM hesabını kullan (varsayılan)** ’ı seçili bırakmanız önerilir.
7. **Uygula** > **Kapat**
8. Intune portalına geri dönün (**ıntune** > **cihaz yapılandırması** > **sertifika bağlayıcıları**). Birkaç dakika sonra yeşil bir onay işareti gösterilir ve **bağlantı durumu** **etkin**olur. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.
9. Ağ ortamınızda bir Web proxy 'niz varsa, bağlayıcının çalışmasını sağlamak için ek yapılandırmalara ihtiyacınız olabilir. Daha fazla bilgi için, bkz. Azure Active Directory belgelerinde [mevcut şirket içi proxy sunucularıyla çalışma](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) .

> [!NOTE]  
> Microsoft Intune Sertifika Bağlayıcısı TLS 1,2 ' i destekler. Bağlayıcıyı barındıran sunucuda TLS 1,2 yüklüyse, bağlayıcı TLS 1,2 ' yi kullanır. Aksi halde TLS 1,1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

## <a name="create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **cihaz yapılandırması** > **profiller** > **Profil oluştur**' a gidin.
    Intune 'a ![Navigate ve güvenilen bir sertifika için yeni bir profil oluşturun ](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

3. **Ayarlar**'a gidin ve daha önce içeri aktarmış olduğunuz .cer dosyası Kök CA Sertifikası'nı girin.

   > [!NOTE]
   > **2. adımda**seçtiğiniz platforma bağlı olarak, sertifika için **Hedef depoyu** seçme seçeneğiniz olabilir veya olmayabilir.

   ![Bir profil oluşturun ve güvenilen bir sertifikayı karşıya yükleyin](./media/certficates-pfx-configure/certificates-pfx-configure-profile-fill.png) 

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](../configuration/device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS sertifika profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **cihaz yapılandırması** > **profiller** > **Profil oluştur**' a gidin.
2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil türü**’nü **PKCS sertifikası** olarak ayarlayın

3. **Ayarlar**' a gidin ve seçtiğiniz platforma uygulanan özellikleri yapılandırın:  
   
   |Ayar     | Platfveyam     | Details   |
   |------------|------------|------------|
   |**Yenileme eşiği (%)**        |Tümü         |Önerilen %20  | 
   |**Sertifika geçerlilik süresi**  |Tümü         |Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanmış olabilir. |
   |**Anahtar depolama sağlayıcısı (KSP)**   |Windows 10  | Windows için, cihazdaki anahtarların depolanacağı yeri seçin. |
   |**Sertifika yetkilisi**      |Tümü         |Kuruluş sertifika yetkilinizin iç tam etki alanı adını (FQDN) görüntüler.  |
   |**Sertifika yetkilisi adı** |Tümü         |Kuruluş SERTIFIKA yetkilinizin adını (örneğin, "contoso sertifika yetkilisi") listeler. |
   |**Sertifika türü**             |Mac OS       |Bir tür seçin: <br> **-** **Kullanıcı** sertifikaları hem Kullanıcı hem de cihaz özniteliklerini, sertifikanın konu ve San 'ını içerebilir. <br><br>**-** **cihaz** sertifikaları, sertifikanın konu ve San 'ına yalnızca cihaz özniteliklerini içerebilir. Cihazı, bilgi noktaları veya diğer paylaşılan cihazlar gibi Kullanıcı-daha az cihazlar gibi senaryolar için kullanın.  <br><br> Bu seçim konu adı biçimini etkiler. |
   |**Konu adı biçimi**          |Tümü         |Çoğu platformda, aksi belirtilmedikçe bu seçeneği **ortak ad** olarak ayarlayın.<br><br>MacOS için, konu adı biçimi sertifika türü tarafından belirlenir. Bu makalenin ilerleyen kısımlarında [macOS Için konu adı biçimi](#subject-name-format-for-macos) bölümüne bakın. |
   |**Konu diğer adı**     |Tümü         |Aksi belirtilmedikçe, bu seçeneği **Kullanıcı asıl adı (UPN)** olarak ayarlayın. |
   |**Genişletilmiş anahtar kullanımı**           |**-** Android Cihaz Yöneticisi <br>**-** Android Enterprise (*cihaz sahibi*, *iş profili*) <br> **-** Windows 10 |Sertifikalar genellikle kullanıcı veya cihazın bir sunucuda kimliğini doğrulayabilmesi için *Istemci kimlik doğrulaması* gerektirir. |
   |**Tüm uygulamaların özel anahtara erişimine izin ver** |Mac OS  |İlişkili Mac cihaz için yapılandırılmış uygulamaların PKCS Certificates özel anahtarına erişimi **sağlamak için '** i ayarlayın. <br><br> Bu ayar hakkında daha fazla bilgi için Apple geliştirici belgelerindeki [yapılandırma profili başvurusunun](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf) sertifika yükü *bölümüne bakın.* |
   |**Kök sertifika**             |**-** Android Cihaz Yöneticisi <br> **-** Android Enterprise (*cihaz sahibi*, *iş profili*) |Daha önce atanmış olan bir kök CA sertifika profili seçin. |

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](../configuration/device-profile-assign.md).

   > [!NOTE]
   > Android kurumsal profiline sahip cihazlarda, PKCS sertifika profili kullanılarak yüklenen sertifikalar cihazda görünmez. Başarılı sertifika dağıtımını onaylamak için, Intune konsolundaki profilin durumunu denetleyin.

### <a name="subject-name-format-for-macos"></a>MacOS için konu adı biçimi

Bir macOS PKCS sertifika profili oluştururken, konu adı biçimi seçenekleri, seçtiğiniz sertifika türüne, **Kullanıcı** veya **cihaza**bağlıdır.  

> [!NOTE]  
> Sonuç sertifika Imzalama Isteğindeki (CSR) konu adı, kaçış karakteri olarak şu karakterlerden birini içerdiğinde [, SCEP için görülen aynı sorun olan](certificates-profile-scep.md#avoid-certificate-signing-requests-with-escaped-special-characters) sertifikaları almak için pcks kullanma konusunda bilinen bir sorun vardır ( ters eğik çizgi \\):
> - \+
> - ;
> - ,
> - =

- **Kullanıcı sertifika türü**  
  *Konu adı biçimi* için biçim seçenekleri iki değişken Içerir: **ortak ad (CN)** ve **e-posta (e)** . **Ortak Ad (CN)** şu iki değerden biri olarak ayarlanabilir:

  - **CN = {{username}}** : kullanıcının janedoe@contoso.com gibi Kullanıcı asıl adı.
  - **CN={{AAD_Device_ID}}** : Azure Active Directory’ye (AD) yeni bir cihaz kaydettiğinizde atanan bir kimlik. Bu kimlik genellikle Azure AD’de kimlik doğrulamak için kullanılır.
  - **CN = {{SERIALNUMBER}}** : genellikle üretici tarafından bir cihazı tanımlamak için kullanılan benzersiz seri numarası (sn).
  - **CN = {{ımekarmsayı}}** : bir cep telefonu tanımlamak Için kullanılan uluslararası mobil ekipman KIMLIĞI (IMEI) benzersiz numarası.
  - **CN = {{OnPrem_Distinguished_Name}}** : *CN = Gamze Etikan, OU = USERACCOUNTS, DC = Corp, DC = contoso, DC = com*gibi virgülle ayrılmış göreli ayırt edici adların sırası.

    *{{OnPrem_Distinguished_Name}}* değişkenini kullanmak Için, Azure AD 'nize [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak *onpremisesdistinguishedname* User özniteliğini eşitlediğinizden emin olun.

  - **CN = {{onPremisesSamAccountName}}** : Yöneticiler, *adlı BIR*özniteliğe Azure AD connect kullanarak sAMAccountName ÖZNITELIĞINI Active Directory 'den Azure AD 'ye eşitleyebilir. Intune, bu değişkeni bir sertifika konusunun sertifika verme isteğinin bir parçası olarak kullanabilir. SamAccountName özniteliği, Windows 'un önceki bir sürümünden (Windows 2000 öncesi) istemcileri ve sunucuları desteklemek için kullanılan Kullanıcı oturum açma adıdır. Kullanıcı oturum açma adı biçimi: EtkiAlanıAdı \ *testuser*veya yalnızca *testuser*.

    *{{OnPremisesSamAccountName}}* değişkenini kullanmak Için, Azure AD 'nize [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak *onPremisesSamAccountName* User özniteliğini eşitlediğinizden emin olun.

  Bu değişkenlerin ve statik dizelerin bir veya birkaç tanesinin bir bileşimini kullanarak aşağıdaki gibi özel bir konu adı biçimi oluşturabilirsiniz:  
  - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
  
  Bu örnekte, CN ve E değişkenlerini kullanan bir konu adı biçimi ve kuruluş birimi, kuruluş, konum, durum ve ülke değerleri için dizeler bulunur. [CertStrToName işlevi](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx), bu işlevi ve desteklenen dizelerini açıklar.

- **Cihaz sertifika türü**  
  Konu adı biçimi için biçim seçenekleri aşağıdaki değişkenleri içerir: 
  - **{{AAD_Device_ID}}**
  - **{{Device_Serial}}**
  - **{{Device_IMEI}}**
  - **{{SerialNumber}}**
  - **{{Imekarmsayı}}**
  - **{{Azureaddeviceıd}}**
  - **{{WiFiMacAddress}}**
  - **{{IMEı}}**
  - **{{Aygıtadı}}**
  - **{{Fullyıqualifieddomainname}}** *(yalnızca Windows ve etki alanına katılmış cihazlar için geçerlidir)*
  - **{{MEıD}}**
   
  Bu değişkenleri ve metin kutusu içinde değişkeni için metni belirtebilirsiniz. Örneğin, *Device1* adlı bir cihazın ortak adı **CN = {{aygıtadı}} Device1**olarak eklenebilir.

  > [!IMPORTANT]  
  > - Bir değişken belirttiğinizde, bir hatadan kaçınmak için, değişken adını örnekte görüldüğü gibi küme ayraçları {} içine alın.  
  > - **IMEI**, **SerialNumber**ve **fullyıqualifieddomainname**gibi bir cihaz sertifikasının *Konu* veya *San* 'ı üzerinde kullanılan cihaz özellikleri, cihaza erişimi olan bir kişi tarafından sızılmış özelliklerdir.
  > - Bir cihazın, bu cihaza yüklemek için bir sertifika profilinde belirtilen tüm değişkenleri desteklemesi gerekir.  Örneğin, bir SCEP profilinin konu adında **{{IMEI}}** kullanılıyorsa ve IMEI numarası olmayan bir cihaza atanırsa, profil yüklenemez.  
 


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

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](../configuration/device-profile-assign.md) ve [durumunu izleyin](../configuration/device-profile-monitor.md).

[Sertifikalar IÇIN SCEP kullanın](certificates-scep-configure.md)veya [bir Symantec PKI Manager Web hizmetinden PKCS sertifikaları verin](certificates-digicert-configure.md).
