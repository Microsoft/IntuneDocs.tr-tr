---
title: Altyapıyı Microsoft Intune-Azure ile SCEP sertifika profillerini destekleyecek şekilde yapılandırma | Microsoft Docs
description: Microsoft Intune içinde SCEP kullanmak için şirket içi AD etki alanınızı yapılandırın, bir sertifika yetkilisi oluşturun, NDES sunucusunu kurun ve Intune sertifika bağlayıcısını kurun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/28/2019
ms.topic: article
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 39858a74cd9503ff40de51ab3680ccf509d25c49
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310953"
---
# <a name="configure-infrastructure-to-support-scep-with-intune"></a>Altyapıyı Intune ile SCEP destekleyecek şekilde yapılandırma  
  
Intune, [uygulamalarınızın ve şirket kaynaklarınızın bağlantılarının kimliğini doğrulamak](certificates-configure.md)için basıt SERTIFIKA kayıt Protokolü (SCEP) kullanımını destekler. SCEP, sertifika Imzalama Isteği (CSR) için ileti değişimini güvenli hale getirmek üzere sertifika yetkilisi (CA) sertifikasını kullanır. Altyapınız SCEP desteklediğinde, sertifikaları cihazlarınıza dağıtmak için Intune *SCEP sertifika* profillerini (Intune 'da bir cihaz profili türü) kullanabilirsiniz. Microsoft Intune Sertifika Bağlayıcısı, bir Active Directory Sertifika Hizmetleri sertifika yetkilisi kullanırken Intune ile SCEP sertifika profillerini kullanmak için gereklidir. [3. taraf sertifika yetkilileri](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration)kullanılırken bağlayıcı gerekli değildir.  

Bu makaledeki bilgiler, Active Directory Sertifika Hizmetleri 'ni kullanırken altyapınızı, SCEP destekleyecek şekilde yapılandırmanıza yardımcı olabilir. Altyapınız yapılandırıldıktan sonra, Intune ile [SCEP sertifika profilleri oluşturabilir ve dağıtabilirsiniz](certificates-profile-scep.md) .  

> [!TIP]  
> Intune, [sertifikaları #12 ortak anahtar şifreleme standartları](certficates-pfx-configure.md)kullanımını da destekler.  


## <a name="prerequisites-for-using-scep-for-certificates"></a>Sertifikalar için SCEP kullanma önkoşulları  
Devam etmeden önce, SCEP sertifika profillerini kullanacak cihazlara [bir *Güvenilen sertifika* profili oluşturduğunuzdan ve dağıttığınızdan](certificates-configure.md#export-the-trusted-root-ca-certificate) emin olun. SCEP sertifika profilleri, cihazları güvenilen bir kök CA sertifikası sağlamak için kullandığınız güvenilen sertifika profiline doğrudan başvurur.  

### <a name="servers-and-server-roles"></a>Sunucular ve sunucu rolleri  
Aşağıdaki şirket içi altyapının, Web uygulaması ara sunucusu dışında Active Directory etki alanına katılmış sunucularda çalışması gerekir.  
- **Sertifika yetkilisi** : Windows Server 2008 R2 Service Pack 1 veya üzeri bir Enterprise sürümünde çalışan bir Microsoft Active Directory Sertifika Hizmetleri kuruluş sertifika YETKILISINI (CA) kullanın. Kullandığınız Windows Server sürümü Microsoft tarafından desteklenen bir sürüm olmalıdır. Tek başına CA desteklenmez. Daha fazla bilgi için bkz. [sertifika yetkilisini yüklemeyi](https://technet.microsoft.com/library/jj125375.aspx). CA 'nız Windows Server 2008 R2 SP1 çalıştırıyorsa, [DÜZELTMEYI KB2483564 adresinden yüklemelisiniz](https://support.microsoft.com/kb/2483564/).  

- **NDES sunucu rolü** – Windows Server 2012 R2 veya sonraki sürümlerde bir ağ cihazı kayıt HIZMETI (NDES) sunucu rolü yapılandırmanız gerekir. Bu makalenin sonraki bir bölümünde [NDES yükleme](#set-up-ndes)sırasında size kılavuzluk ederiz.  

  - NDES 'yi barındıran sunucu, kuruluş sertifika yetkiliniz ile aynı ormanda ve etki alanına katılmış olmalıdır.  
  - Kurumsal CA 'yı barındıran sunucuda yüklü NDES 'yi kullanamazsınız.  
  - Microsoft Intune sertifikası bağlayıcısını NDES 'yi barındıran sunucuya yüklersiniz.  

  NDES hakkında daha fazla bilgi edinmek için Windows Server belgelerindeki [ağ aygıtı kayıt hizmeti Kılavuzu](https://technet.microsoft.com/library/hh831498.aspx) ' na bakın ve [ağ cihazı kayıt hizmeti Ile bir ilke modülü](https://technet.microsoft.com/library/dn473016.aspx)kullanın.  

- **Microsoft Intune sertifika Bağlayıcısı** : Microsoft Intune sertifika Bağlayıcısı, ıNTUNE ile SCEP sertifika profillerini kullanmak için gereklidir. Bu makale, [Bu bağlayıcıyı yükleme](#install-the-intune-certificate-connector)sırasında size kılavuzluk eder.  

  Bağlayıcı Federal bilgi Işleme standardı (FIPS) modunu destekler. FIPS gerekli değildir, ancak etkinleştirildiğinde sertifika verebilir ve iptal edebilirsiniz.  
  - Bağlayıcının Windows Server 2012 R2 veya üstünü çalıştıran bir sunucu olan NDES sunucu rolüyle aynı sunucuda çalışması gerekir.  
  - .NET 4,5 Framework Bağlayıcısı için gereklidir ve Windows Server 2012 R2 'ye otomatik olarak dahildir.  
  - Internet Explorer Artırılmış Güvenlik Yapılandırması [NDES ve Microsoft Intune sertifika Bağlayıcısı barındıran sunucuda devre dışı](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx) bırakılmalıdır.  

Aşağıdaki şirket içi altyapı isteğe bağlıdır:  
  İnternet üzerindeki cihazların sertifika almasını sağlamak için, NDES URL 'nizi kurumsal ağınız için harici olarak yayımlamanız gerekir. Azure AD Uygulama Ara Sunucusu, Web uygulaması ara sunucusu ya da başka bir ters proxy kullanabilirsiniz.
  
- **Azure ad uygulama ara sunucusu** (isteğe bağlı) – NDES URL 'nizi Internet 'te yayımlamak için adanmış bir Web uygulaması proxy (WAP) sunucusu yerine Azure AD uygulama ara sunucusu kullanabilirsiniz. Bu, hem intranet hem de internet 'e yönelik cihazların sertifikaları almasına olanak tanır. Daha fazla bilgi için bkz. [Şirket içi uygulamalara güvenli uzaktan erişim sağlama](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy). 

- **Web uygulaması ara sunucusu** (isteğe bağlı)-NDES URL 'nizi internet 'e yayımlamak Için Windows Server 2012 R2 veya üstünü çalıştıran bir sunucuyu Web uygulaması ara sunucusu (WAP) sunucusu olarak kullanın.  Bu, hem intranet hem de internet 'e yönelik cihazların sertifikaları almasına olanak tanır.

  WAP 'yi barındıran sunucu, ağ cihazı kayıt hizmeti tarafından kullanılan uzun URL 'Ler için destek sağlayan [bir güncelleştirme yüklemelidir](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) . Bu güncelleştirme, [aralık 2014 güncelleştirme toplamasına](https://support.microsoft.com/kb/3013769)dahildir veya [KB3011135](https://support.microsoft.com/kb/3011135)adresinden ayrı ayrı.  

  WAP sunucusunun, dış istemcilere yayımlanan adla eşleşen bir SSL sertifikası olmalı ve NDES hizmetini barındıran bilgisayarda kullanılan SSL sertifikasına güvenmelidir. Bu sertifikalar, WAP sunucusunun istemcilerden gelen SSL bağlantısını sonlandırmayı ve NDES hizmetine yeni bir SSL bağlantısı oluşturmasını sağlar.  

  Daha fazla bilgi için bkz. WAP [için sertifikaları planlayın](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) ve [WAP sunucuları hakkında genel bilgiler](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

### <a name="accounts"></a>Hesaplar   
- **NDES hizmet hesabı** -NDES 'yi ayarlamadan önce, NDES hizmet hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı belirleyin. Bu hesabı, sertifika veren SERTIFIKA yetkilinizdeki şablonları yapılandırırken, NDES 'ı yapılandırmadan önce belirtirsiniz.  

  Bu hesabın NDES 'yi barındıran sunucuda aşağıdaki haklara sahip olması gerekir:  
  - **Yerel olarak oturum aç**  
  - **Hizmet olarak oturum açma**  
  - **Toplu iş olarak oturum açma**  

  Daha fazla bilgi için bkz. [NDES hizmet hesabı olarak davranacak bir etki alanı kullanıcı hesabı oluşturma](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11)#to-create-a-domain-user-account-to-act-as-the-ndes-service-account). 
- **NDES hizmetini barındıran bilgisayara erişim** -Windows Server rollerini NDES 'yi yüklediğiniz sunucuya yüklemek ve yapılandırmak için gerekli izinlere sahip bir etki alanı kullanıcı hesabına ihtiyacınız vardır.  

- **Sertifika yetkilisine erişim** -sertifika yetkilinizi yönetme haklarına sahip bir etki alanı kullanıcı hesabına ihtiyacınız vardır.  

### <a name="network-requirements"></a>Ağ gereksinimleri

NDES hizmetini [Azure AD uygulama proxy 'si, Web erişimi proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/)veya üçüncü taraf ara sunucu gibi bir ters proxy üzerinden yayımlamayı öneririz. Ters proxy kullanmıyorsanız, bağlantı noktası 443 üzerinde internet 'teki tüm konaklardan ve IP adreslerinden NDES hizmetine TCP trafiğine izin verin.  

NDES hizmeti ile ortamınızdaki herhangi bir destekleyici altyapı arasındaki iletişim için gereken tüm bağlantı noktalarına ve protokollere izin verin. Örneğin, NDES hizmetini barındıran bilgisayarın CA, DNS sunucuları, etki alanı denetleyicileri ve ortamınızdaki diğer hizmet veya sunucularla (Configuration Manager gibi) iletişim kurması gerekir.

### <a name="certificates-and-templates"></a>Sertifikalar ve şablonlar

SCEP kullandığınızda aşağıdaki sertifikalar ve şablonlar kullanılır.

|Nesne    |Ayrıntılar    |
|----------|-----------|
|**SCEP sertifika şablonu**         |Sertifika veren SERTIFIKA yetkiliniz üzerinde, cihazların SCEP isteklerini fulll olarak kullanılacak şablon. |
|**İstemci kimlik doğrulama sertifikası** |Sertifika veren CA 'nızdan veya genel CA 'dan istendi.<br /> Bu sertifikayı NDES hizmetini barındıran bilgisayara yüklersiniz ve Intune sertifika Bağlayıcısı tarafından kullanılır.<br /> Sertifika, bu sertifikayı vermek için kullandığınız CA şablonunda *istemci* ve *sunucu kimlik doğrulaması* anahtar kullanımları (**Gelişmiş anahtar kullanımları**) içeriyorsa. Daha sonra sunucu ve istemci kimlik doğrulaması için aynı sertifikayı kullanabilirsiniz. |
|**Sunucu kimlik doğrulama sertifikası** |Sertifika veren CA 'nızdan veya genel CA 'dan istenen Web sunucusu sertifikası.<br /> Bu SSL sertifikasını, NDES 'yi barındıran bilgisayarda IIS 'ye yükler ve bağlarsınız.<br />Sertifika, bu sertifikayı vermek için kullandığınız CA şablonunda *istemci* ve *sunucu kimlik doğrulaması* anahtar kullanımları (**Gelişmiş anahtar kullanımları**) içeriyorsa. Daha sonra sunucu ve istemci kimlik doğrulaması için aynı sertifikayı kullanabilirsiniz. |
|**Güvenilen kök CA sertifikası**       |Bir SCEP sertifika profili kullanmak için cihazların güvenilen kök sertifika yetkilinizin (CA) güvenmesi gerekir. Güvenilen kök CA sertifikasını kullanıcılara ve cihazlara sağlamak için Intune 'da bir *Güvenilen sertifika profili* kullanın. <br/><br/> **-**  İşletim sistemi platformu başına tek bir güvenilen kök CA sertifikası kullanın ve bu sertifikayı, oluşturduğunuz her bir güvenilen sertifika profiliyle ilişkilendirin. <br /><br /> **-**  Gerektiğinde ek Güvenilen kök CA sertifikaları kullanabilirsiniz. Örneğin, Wi-Fi erişim noktalarınız için sunucu kimlik doğrulama sertifikalarını imzalayan bir CA 'ya güven sağlamak üzere ek sertifikalar kullanabilirsiniz. CA 'Lar yayımlamak için ek Güvenilen kök CA sertifikaları oluşturun.  Intune 'da oluşturduğunuz SCEP sertifika profilinde, veren CA için güvenilen kök CA profilini belirttiğinizden emin olun.<br/><br/> Güvenilen sertifika profili hakkında daha fazla bilgi için bkz. [Güvenilen kök CA sertifikasını dışarı aktarma](certificates-configure.md#export-the-trusted-root-ca-certificate) ve [Güvenilen sertifika profilleri oluşturma](certificates-configure.md#create-trusted-certificate-profiles) ' da *Intune 'Da kimlik doğrulaması için sertifikaları kullanma*. |

## <a name="configure-the-certification-authority"></a>Sertifika yetkilisini yapılandırma

Aşağıdaki bölümlerde şunları yapmanız gerekir:
- NDES için gerekli şablonu yapılandırın ve yayımlayın. 
- Sertifika iptali için gerekli izinleri ayarlayın. 

Aşağıdaki bölümlerde Windows Server 2012 R2 veya üzeri bilgileri ve Active Directory Sertifika Hizmetleri (AD CS) bilgisi gerekir.  

### <a name="access-your-issuing-ca"></a>Sertifika veren CA 'nize erişin

1. CA 'yı yönetmek için yeterli haklara sahip bir etki alanı hesabıyla, sertifika veren CA 'da oturum açın.  
2. Sertifika yetkilisi Microsoft Yönetim Konsolu 'nu (MMC) açın. ' Certsrv. msc ' öğesini **çalıştırın** veya **Sunucu Yöneticisi**' de **Araçlar**' a ve ardından **sertifika yetkilisi**' ne tıklayın.
3. **Sertifika şablonları** düğümünü seçin, **eylem** > **Yönet**' e tıklayın.

### <a name="create-the-scep-certificate-template"></a>SCEP sertifika şablonu oluşturma

1. SCEP sertifika şablonu olarak kullanmak üzere bir v2 sertifika şablonu (Windows 2003 uyumlulukla birlikte) oluşturun. Yapabilecekleriniz:  
   - *Sertifika şablonları* ek bileşenini kullanarak yeni bir özel şablon oluşturun.  
   - Var olan bir şablonu (Kullanıcı şablonu gibi) kopyalayın ve ardından NDES şablonu olarak kullanılacak kopyayı güncelleştirin.
 
2. Şablonun belirtilen sekmelerinde aşağıdaki ayarları yapılandırın:
   - **Genel**:
     - **Active Directory Sertifika Yayımla**seçeneğinin işaretini kaldırın.
     - Bu şablonu daha sonra tanımlayabilmeniz için kolay bir **şablon görünen adı** belirtin.  

   - **Konu adı**:  
     - **Istekte tedarik '** ı seçin. Güvenlik, NDES için Intune ilke modülü tarafından zorlanır.  

     ![Şablon, konu adı sekmesi](./media/certificates-scep-configure/scep-ndes-subject-name.jpg)
   - **Uzantılar**:  
     - **Uygulama Ilkelerinin açıklamasının** **istemci kimlik doğrulamasını**içerdiğinden emin olun.  
       > [!IMPORTANT]  
       > Yalnızca gerekli olan uygulama ilkelerini ekleyin. Güvenlik yöneticileriniz ile seçimlerinizi onaylayın.
 
     - İOS ve macOS sertifika şablonları için Ayrıca **anahtar kullanımını** düzenleyin ve **imzanın kaynak kanıtı olmadığından** emin olun.

     ![Şablon, uzantılar sekmesi](./media/certificates-scep-configure/scep-ndes-extensions.jpg)  

   - **Güvenlik**:  
     - **NDES hizmet hesabını**ekleyin. Bu hesabın bu şablon için **okuma** ve **kaydetme** izinleri olması gerekir.

     - , SCEP profilleri oluşturacak olan Intune yöneticileri için ek hesaplar ekleyin. Bu hesapların, bu yöneticilerin SCEP profilleri oluştururken bu şablona gözatmasını sağlamak için şablonda **okuma** izinleri olması gerekir.  

     ![Şablon, güvenlik sekmesi](./media/certificates-scep-configure/scep-ndes-security.jpg)  

   - **Istek işleme**:  
      Aşağıdaki resim bir örnektir. Yapılandırmanız farklılık gösterebilir.  

     ![Şablon, istek işleme sekmesi](./media/certificates-scep-configure/scep-ndes-request-handling.png) 

   - **Verme gereksinimleri**:  
     Aşağıdaki resim bir örnektir. Yapılandırmanız farklılık gösterebilir.  

     ![Şablon, verme gereksinimleri sekmesi](./media/certificates-scep-configure/scep-ndes-issuance-reqs.jpg)  

3. Sertifika şablonunu kaydedin.  

### <a name="create-the-client-certificate-template"></a>İstemci sertifikası şablonu oluşturma

Intune sertifika Bağlayıcısı, *Istemci kimlik doğrulaması* gelişmiş anahtar kullanımı ve konu adı, bağlayıcının YÜKLENDIĞI makinenin FQDN 'sine eşit olan bir sertifika gerektirir. Aşağıdaki özelliklere sahip bir şablon gereklidir:

- @No__t **uzantıları**-1**uygulama Ilkeleri** **istemci kimlik doğrulaması** içermelidir
- **Konu adı** > **arz isteği**.

Bu özellikleri içeren bir şablonunuz zaten varsa, onu yeniden kullanabilir, aksi halde var olan bir şablonu çoğaltıp ya da özel bir şablon oluşturarak yeni bir şablon oluşturabilirsiniz.

### <a name="create-the-server-certificate-template"></a>Sunucu sertifikası şablonu oluşturma

NDES sunucusundaki yönetilen cihazlar ve IIS arasındaki iletişimler, sertifika kullanımını gerektiren HTTPS kullanır. Bu sertifikayı vermek için **Web sunucusu** sertifika şablonunu kullanabilirsiniz. Ya da özel bir şablon bulundurmayı tercih ediyorsanız, aşağıdaki özellikler gereklidir:

- @No__t **uzantıları**-1**uygulama Ilkeleri** **sunucu kimlik doğrulaması** içermelidir
- **Konu adı** > **arz isteği**.

> [!NOTE]  
> İstemci ve sunucu sertifikası şablonlarından her iki gereksinimi karşılayan bir sertifikanız varsa, hem IIS hem de Intune sertifika Bağlayıcısı için tek bir sertifika kullanabilirsiniz.

### <a name="grant-permissions-for-certificate-revocation"></a>Sertifika iptali için izin verme

Intune 'un artık gerekli olmayan sertifikaları iptal edebilmesi için, sertifika yetkilisinde izin vermeniz gerekir. 

Intune sertifika Bağlayıcısı ' nde, NDES Server **sistem hesabını** veya **NDES hizmet hesabı**gibi belirli bir hesabı kullanabilirsiniz.

1. Sertifika yetkilisi konsolunuza CA adına sağ tıklayın ve **Özellikler**' i seçin.
2. **Güvenlik** sekmesinde **Ekle**' ye tıklayın.
3. **Sertifika verme ve yönetme** izni:
   - NDES Server **sistem hesabını**kullanmayı tercih EDIYORSANıZ, NDES sunucusu için izinleri belirtin.
   - **NDES hizmet hesabını**kullanmayı tercih ederseniz, bunun yerine bu hesap için izinler sağlayın.

### <a name="modify-the-validity-period-of-the-certificate-template"></a>Sertifika şablonunun geçerlilik süresini değiştirme

Sertifika şablonunun geçerlilik süresini değiştirmek isteğe bağlıdır.  

[SCEP sertifika şablonunu](#create-the-scep-certificate-template)oluşturduktan sonra, **genel** sekmesindeki **geçerlilik süresini** gözden geçirmek için şablonu düzenleyebilirsiniz.  

Varsayılan olarak, Intune şablonda yapılandırılan değeri kullanır. Ancak, CA 'yı istekte bulunan kişinin farklı bir değer girmesine izin verecek şekilde yapılandırabilir ve bu değer Intune konsolu içinden ayarlanabilir.  

> [!IMPORTANT]  
> İOS ve macOS için her zaman şablonda bir değer kümesi kullanın.  

#### <a name="to-configure-a-value-that-can-be-set-from-within-the-intune-console"></a>Intune konsolu içinden ayarlanabilir bir değer yapılandırmak için  
1. CA 'da aşağıdaki komutları çalıştırın:  
   -**certutil-setreg ilkeeditflags + EDITF_ATTRIBUTEENDDATE**  
   -**net stop CertSvc**  
   -**net start CertSvc**  

2. Sertifika veren CA 'da, sertifika şablonunu yayımlamak için sertifika yetkilisi ek bileşenini kullanın. **Sertifika şablonları** düğümünü seçin, **eylem** > **Yeni** > **sertifika şablonu**' nu seçin ve ardından önceki bölümde oluşturduğunuz sertifika şablonunu seçin.  

3. Şablonun **sertifika şablonları** klasöründe görüntüleyerek yayımlandığını doğrulayın.  

## <a name="set-up-ndes"></a>NDES 'yi ayarlama  
Aşağıdaki yordamlar, Intune ile kullanmak üzere ağ cihazı kayıt hizmeti 'ni (NDES) yapılandırmanıza yardımcı olabilir. NDES hakkında daha fazla bilgi için bkz. [ağ cihazı kayıt hizmeti Kılavuzu](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v%3dws.11)).  

### <a name="install-the-ndes-service"></a>NDES hizmetini yükler  
1. NDES hizmetinizi barındıracak sunucuda bir **Kuruluş Yöneticisi**olarak oturum açın ve ardından NDES 'yi yüklemek için [rol ve Özellik Ekleme Sihirbazı](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) ' nı kullanın:

   1. Sihirbazda, AD CS rol hizmetlerine erişim kazanmak için **Active Directory Sertifika Hizmetleri** ' ni seçin. **Ağ cihazı kayıt hizmeti**' ni seçin, **sertifika yetkilisinin**işaretini kaldırın ve Sihirbazı doldurun.  

      > [!TIP]  
      > **Yükleme ilerlemesi**' nde **Kapat**' ı seçmeyin. Bunun yerine, **hedef sunucuda Active Directory Sertifika Hizmetlerini Yapılandır** bağlantısını seçin. **AD CS yapılandırma** Sihirbazı açılarak, bu makalede yer aldığı sonraki YORDAMDA kullanacağınız *NDES hizmetini yapılandırın*. AD CS yapılandırması açıldıktan sonra, rol ve Özellik Ekleme Sihirbazı 'nı kapatabilirsiniz.  

   2. NDES sunucuya eklendiğinde, sihirbaz IIS de yüklenir. IIS 'nin aşağıdaki yapılandırmalara sahip olduğunu doğrulayın:  

      - **Web sunucusu** > **güvenlik** > **istek filtreleme**  
      - **Web sunucusu** > **uygulama geliştirme** > **ASP.NET 3,5**  

        ASP.NET 3,5 yüklemesi .NET Framework 3,5 ' dir. .NET Framework 3,5 yüklenirken hem çekirdek **.NET Framework 3,5** özelliği hem de **HTTP etkinleştirmesi**' ni yükler.  
      - **Web sunucusu** > **uygulama geliştirme** > **ASP.NET 4,5**  

        ASP.NET 4,5 yüklemesi .NET Framework 4,5 ' dir. .NET Framework 4,5 yüklenirken, çekirdek **.NET Framework 4,5** özelliği, **ASP.NET 4,5**ve **WCF Hizmetleri** > **http etkinleştirme** özelliğini yüklemeniz gerekir.  

      - **Yönetim araçları** > **IIS 6 Yönetim uyumluluğu** > **IIS 6 Metatabanı Uyumluluğu**  
      - **Yönetim araçları** > **IIS 6 Yönetim uyumluluğu** > **IIS 6 WMI Uyumluluğu**  
      - Sunucuda, NDES hizmet hesabını yerel **IIS_IUSR** grubunun bir üyesi olarak ekleyin.  

2. NDES hizmetini barındıran bilgisayarda, yükseltilmiş bir komut isteminde aşağıdaki komutu çalıştırın. Aşağıdaki komut NDES hizmet hesabının SPN 'sini ayarlar:  

   `setspn -s http/<DNS name of the computer that hosts the NDES service> <Domain name>\<NDES Service account name>`
   
   Örneğin, NDES hizmetini barındıran bilgisayar **server01**olarak adlandırılmışsa, etki alanınız **contoso.com**ve hizmet hesabı **NdesService**ise şunu kullanın:  

   `setspn –s http/Server01.contoso.com contoso\NDESService`  

### <a name="configure-the-ndes-service"></a>NDES hizmetini yapılandırma  

1. NDES hizmetini barındıran bilgisayarda, **AD CS yapılandırma** sihirbazını açın ve aşağıdaki güncelleştirmeleri yapın:  

   > [!TIP]  
   > Son yordamdan devam ediyorsanız ve **hedef sunucu bağlantısındaki Active Directory Sertifika Hizmetleri** 'ni tıklattıysanız, bu sihirbazın zaten açık olması gerekir. Aksi takdirde, Active Directory Sertifika Hizmetleri için dağıtım sonrası yapılandırmaya erişmek üzere Sunucu Yöneticisi açın.  

   - **Rol hizmetleri**' nde **ağ aygıtı kayıt hizmeti**' ni seçin.
   - **NDES Için hizmet hesabı**' nda, NDES hizmet hesabını belirtin.
   - **NDES Için CA**'da **Seç**' e tıklayın ve ardından sertifika şablonunu yapılandırdığınız veren CA 'yı seçin.
   - **NDES Için şifreleme**bölümünde, anahtar uzunluğunu Şirket gereksinimlerinizi karşılayacak şekilde ayarlayın.
   - **Onaylama**bölümünde, Sihirbazı gerçekleştirmek için **Yapılandır** ' ı seçin.

2. Sihirbaz tamamlandıktan sonra, NDES hizmetini barındıran bilgisayardaki aşağıdaki kayıt defteri anahtarını güncelleştirin:  
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`  

   Bu anahtarı güncelleştirmek için, sertifika şablonlarının **amacını** ( **istek işleme** sekmesinde bulunur) tanımla. Ardından, var olan verileri sertifika [şablonu](#create-the-scep-certificate-template)oluştururken belirttiğiniz sertifika şablonu adıyla (şablonun görünen adı değil) değiştirerek ilgili kayıt defteri girişini güncelleştirin.  

   Aşağıdaki tabloda, sertifika şablonu amacı kayıt defterindeki değerlerle eşlenir:
   
   |Sertifika şablonu amacı (Istek Işleme sekmesinde)|Düzenlenecek kayıt defteri değeri|SCEP profili için Intune yönetim konsolunda görülen değer|
   |------------------------|-------------------------|---|
   |İmza               |SignatureTemplate        |Dijital Imza |
   |Şifreleme              |EncryptionTemplate       |Anahtar şifreleme  |
   |İmza ve şifreleme|GeneralPurposeTemplate   |Anahtar şifreleme<br/>Dijital Imza |  

   Örneğin, sertifika şablonunuzun amacı **şifreleme**Ise **EncryptionTemplate** değerini sertifika şablonunuzun adı olacak şekilde düzenleyin.  

3. NDES hizmetinin aldığı uzun URL 'Ler (sorgular) için IIS 'de destek eklemek üzere IIS istek filtrelemeyi yapılandırın.
   1. IIS Yöneticisi 'nde **varsayılan Web sitesi** > **istek filtreleme** > **özellik ayarını** Düzenle ' yi seçerek **istek filtreleme ayarlarını Düzenle** sayfasını açın.  

   2. Aşağıdaki ayarları yapılandırın:  
      - **URL uzunluğu üst sınırı (bayt)** = 65534  
      - **En fazla sorgu dizesi (bayt)** = 65534  
   3. Bu yapılandırmayı kaydetmek ve IIS Yöneticisi 'ni kapatmak için **Tamam** ' ı seçin.  
   4. Belirtilen değerlere sahip olduğunu doğrulamak için aşağıdaki kayıt defteri anahtarını görüntüleyerek bu yapılandırmayı doğrulayın:  

      `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`    

      Aşağıdaki değerler DWORD girdileri olarak ayarlanır:  
      - Ad: **MaxFieldLength**, ondalık değeri **65534** ile  
      - Ad: **MaxRequestBytes**, ondalık değeri **65534** ile  
4. NDES hizmetini barındıran sunucuyu yeniden başlatın. **IISReset**kullanmayın; iireset gerekli değişiklikleri tamamlayamıyor.  

5. *Http://* Server_FQDN */certsrv/mscep/mscep.dll*adresine göz atın. Aşağıdaki görüntüye benzer bir NDES sayfası görmeniz gerekir:  

   ![Test NDES](./media/certificates-scep-configure/scep-ndes-url.png)
  
   Web adresi **503 hizmetini devre dışı**döndürürse, bilgisayarlar Olay Görüntüleyicisi ' ni kontrol edin. Bu hata genellikle, [NDES hizmet hesabı için](#accounts)eksik bir izin nedeniyle uygulama havuzu durdurulduğunda oluşur.  
  
### <a name="install-and-bind-certificates-on-the-server-that-hosts-ndes"></a>NDES 'yi barındıran sunucuya sertifika yükleyip bağlama  
> [!TIP]  
> Aşağıdaki yordamda, hem *sunucu kimlik doğrulaması* hem de *istemci kimlik doğrulaması* için, bu sertifika her iki kullanımlar için ölçütlere uyacak şekilde yapılandırıldığında tek bir sertifika kullanabilirsiniz. Her kullanım ölçütü aşağıdaki yordamın 1. ve 3. adımlarında açıklanmıştır.  

1. İç Sertifika yetkilinizden veya genel CA 'dan bir **sunucu kimlik doğrulama** sertifikası isteyin ve sertifikayı sunucuya yükler.  

   Sunucu, tek bir ağ adresi için bir dış ve iç ad kullanıyorsa, sunucu kimlik doğrulama sertifikasının olması gerekir:  

   - Dış genel sunucu adına sahip bir **Konu adı** .
   - İç sunucu adını içeren bir **Konu diğer adı** .  

2. Sunucu kimlik doğrulama sertifikasını IIS 'de bağlayın:  
  
   1. Sunucu kimlik doğrulama sertifikasını yükledikten sonra **IIS Yöneticisi**' ni açın ve **varsayılan Web sitesi**' ni seçin. **Eylemler** bölmesinde **bağlamalar**' ı seçin.  
   1. **Ekle**' yi seçin, **tür** ' ü **https**olarak ayarlayın ve bağlantı noktası **443**olduğunu onaylayın.  
   1. **SSL sertifikası**için sunucu kimlik doğrulama sertifikasını belirtin.  
 
3. NDES Sunucunuzda, iç CA 'nızdan veya bir genel sertifika yetkilisinden bir **istemci kimlik doğrulama** sertifikası isteyin ve bu sertifikayı yükledikten sonra.  

   İstemci kimlik doğrulama sertifikasının aşağıdaki özelliklere sahip olması gerekir:  
   - **Gelişmiş anahtar kullanımı**: Bu değer **istemci kimlik doğrulaması**içermelidir.  
   - **Konu adı**: değer, sertifikayı yüklemekte olduğunuz sunucunun DNS ADıNA (NDES sunucusu) eşit olmalıdır.  

4. NDES hizmetini barındıran sunucu artık Intune sertifika bağlayıcısını desteklemeye hazırdır.  

## <a name="install-the-intune-certificate-connector"></a>Intune sertifika bağlayıcısını yükler  
Microsoft Intune Sertifika Bağlayıcısı NDES hizmetinizi çalıştıran sunucuya yüklenir. NDES veya Intune sertifika bağlayıcısının, veren sertifika yetkiliniz (CA) ile aynı sunucuda kullanılması desteklenmez.  

Sertifika bağlayıcısını yüklemek için:  
1. Intune 'a yönelik haklara sahip bir hesapla [Intune portalında](https://aka.ms/intuneportal) oturum açın.  

2. **Cihaz yapılandırma** > **sertifika yetkilisi** > **Ekle**' yi seçin.  

3. SCEP dosyası için bağlayıcıyı indirin ve kaydedin. Bağlayıcıyı yükleyeceğiniz sunucudan erişilebilen bir konuma kaydedin.

   ![ConnectorDownload](./media/certificates-scep-configure/download-certificates-connector.png)

4. Yükleme tamamlandıktan sonra, ağ cihazı kayıt hizmeti (NDES) rolünü barındıran sunucuya gidin. Ardından:  

   1. Intune sertifika bağlayıcısının gerektirdiği gibi .NET 4,5 Framework 'Ün yüklü olduğunu doğrulayın. .NET 4,5 Framework, Windows Server 2012 R2 ve daha yeni sürümlere otomatik olarak dahildir.  
   2. Yükleyiciyi çalıştırın (**Ndesconnectorsetup. exe**). Yükleyici ayrıca NDES için ilke modülünü ve IIS sertifika kayıt noktası (CRP) Web hizmetini de yüklüyor. Web ağ hizmeti olan, *Certificateregistrationsvc*, IIS 'de bir uygulama olarak çalışır.  

      - Tek başına Intune için NDES yüklediğinizde, CRP hizmeti sertifika Bağlayıcısı ile otomatik olarak yüklenir. 
      - Intune 'u Configuration Manager kullandığınızda, sertifika kayıt noktasını Configuration Manager bir site sistemi rolü olarak yüklersiniz.  
5. Sertifika Bağlayıcısı için istemci sertifikası istendiğinde, **Seç**' i seçin ve, sertifikaları yükleme ve bağlama yordamının adım #3 sırasında NDES sunucunuza yüklediğiniz **istemci kimlik doğrulaması** sertifikasını seçin [. ](#install-and-bind-certificates-on-the-server-that-hosts-ndes)Bu makalenin önceki KıSıMLARıNDA NDES 'yi barındıran sunucu.  

   İstemci kimlik doğrulama sertifikasını seçtikten sonra, **Microsoft Intune sertifika Bağlayıcısı yüzeyi Için Istemci sertifikasına** geri dönersiniz. Seçtiğiniz sertifika gösterilmese de bu sertifikanın özelliklerini görüntülemek için **İleri** ' yi seçin. **İleri**' yi ve ardından **uygulamasını**seçin.

6. Sihirbaz tamamlandıktan sonra, Sihirbazı kapatmadan önce, **sertifika Bağlayıcısı Kullanıcı arabirimini başlatın**.  

   Sertifika Bağlayıcısı Kullanıcı arabirimini çalıştırmadan önce Sihirbazı kapatırsanız, aşağıdaki komutu çalıştırarak yeniden açabilirsiniz: *< install_Path > \NDESConnectorUI\NDESConnectorUI.exe*

7. **Sertifika Bağlayıcısı** Kullanıcı arabiriminde:  
   1. **Oturum aç**' ı seçin ve Intune Hizmet Yöneticisi kimlik bilgilerinizi veya genel yönetim izni olan bir kiracı yöneticisinin kimlik bilgilerini girin.  
   2. Kullandığınız hesaba geçerli bir Intune lisansı atanmalıdır.  
   3. Oturum açtıktan sonra, Intune sertifika Bağlayıcısı bir sertifikayı Intune 'dan indirir. Bu sertifika, bağlayıcı ve Intune arasında kimlik doğrulaması için kullanılır. Kullandığınız hesapta bir Intune lisansı yoksa, bağlayıcı (Ndesconnectoruı. exe) sertifikayı Intune 'dan alamaz.  

      Kuruluşunuz bir ara sunucu kullanıyorsa ve NDES sunucusunun Internet 'e erişmesi için ara sunucu gerekiyorsa, **proxy sunucusu kullan**' ı seçin. Ardından, bağlanmak için proxy sunucu adı, bağlantı noktası ve hesap kimlik bilgilerini girin.  

    4. **Gelişmiş** sekmesini seçin ve ardından sertifika verme **ve yönetme** iznine sahip olan bir hesabın kimlik bilgilerini veren sertifika yetkiliniz üzerinde girin. Değişikliklerinizi **uygulayın** .  

    5. Artık sertifika Bağlayıcısı Kullanıcı arabirimini kapatabilirsiniz.  

8. Bir komut istemi açın, **Services. msc**yazın ve ardından **girin**. @No__t-1**yeniden başlatma** **Intune Bağlayıcısı hizmetine**sağ tıklayın.


Hizmetin çalıştığını doğrulamak için bir tarayıcı açın ve aşağıdaki URL 'YI girin. **403** hatası döndürmelidir: `https://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`  

> [!NOTE]  
> Intune sertifika Bağlayıcısı TLS 1,2 ' i destekler. Bağlayıcıyı barındıran sunucu TLS 1,2 ' i destekliyorsa, TLS 1,2 kullanılır. Sunucu TLS 1,2 ' i desteklemiyorsa TLS 1,1 kullanılır. Şu anda, cihazlar ve sunucu arasında kimlik doğrulaması için TLS 1,1 kullanılır.

## <a name="next-steps"></a>Sonraki adımlar

[SCEP sertifika profili oluşturma](certificates-profile-scep.md)  
[Intune sertifika Bağlayıcısı sorunlarını giderme](troubleshoot-certificate-connector-events.md)
