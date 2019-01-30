---
title: Microsoft Intune - Azure ile SCEP sertifikalarını kullanma | Microsoft Docs
description: Microsoft Intune’da SCEP sertifikalarını kullanmak için şirket içi AD etki alanınızı yapılandırın, bir sertifika yetkilisi oluşturun, NDES sunucusunu ayarlayın ve Intune Sertifika Bağlayıcısı’nı yükleyin. Daha sonra bir SCEP sertifika profili oluşturun ve ardından bu profili gruplara atayın. Ayrıca, farklı olay kimlikleriyle bunların açıklamalarını ve Intune bağlayıcı hizmeti için tanılama kodlarını görün.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 1/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f8b4d1aded0198dfc3dcccf6bdeda30bb54ee651
ms.sourcegitcommit: 0142020a7cd75348c6367facf072ed94238e667f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55230163"
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>Intune ile SCEP sertifikalarını yapılandırma ve kullanma

Bu makale, altyapınızın nasıl yapılandırılacağı ve ardından Intune ile Basit Sertifika Kayıt Protokolü (SCEP) sertifika profillerinin nasıl oluşturulup atanacağını gösterir.

## <a name="configure-on-premises-infrastructure"></a>Şirket içi altyapıyı yapılandırma

- **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucular (Web Uygulaması Ara Sunucusu hariç), Active Directory etki alanınıza katılmalıdır.

- **Sertifika yetkilisi** (CA): Bir Microsoft sertifika yetkilisi (Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan kuruluş CA) olması gerekir. Tek Başına CA desteklenmez. Ayrıntılar için bkz. [Sertifika Yetkilisi'ni yükleme](http://technet.microsoft.com/library/jj125375.aspx).
    CA'nız Windows Server 2008 R2 çalıştırıyorsa, [KB2483564 ile gelen düzeltmeyi yüklemeniz](http://support.microsoft.com/kb/2483564/)gerekir.

- **NDES sunucusu**: Bir Windows Server 2012 R2 veya sonraki sürümlerde, ağ cihazı kayıt hizmeti (NDES) sunucusu rolü ayarlayın. Intune, Enterprise CA çalıştıran bir sunucuda NDES kullanımını desteklemez. Windows Server 2012 R2’yi NDES’yi barındıracak şekilde yapılandırma yönergeleri için bkz. [Ağ Cihazı Kayıt Hizmeti Kılavuzu](http://technet.microsoft.com/library/hh831498.aspx).
NDES sunucusu, Enterprise CA ile aynı ormanda bulunan bir etki alanına katılmış olmalıdır. NDES sunucusunu ayrı bir ormanda, yalıtılmış ağda veya iç etki alanında dağıtma hakkında daha fazla bilgi, [Ağ Cihazı Kayıt Hizmeti ile İlke Modülü Kullanma](https://technet.microsoft.com/library/dn473016.aspx) başlığı altında bulunabilir.

- **Microsoft Intune sertifika Bağlayıcısı**: İndirme **sertifika Bağlayıcısı** Yükleyicisi (**NDESConnectorSetup.exe**) Intune Yönetim Portalı'ndan. NDES rolüne sahip bir sunucuda bu yükleyiciyi çalıştırın.  

  - NDES Sertifika bağlayıcısı, Federal Bilgi İşleme Standardı (FIPS) modunu da destekler. FIPS gerekli değildir ancak etkinleştirildiğinde sertifika verebilir ve iptal edebilirsiniz.

- **Web uygulaması Ara sunucusu** (isteğe bağlı): Windows Server 2012 R2 çalıştıran bir sunucu kullanın veya daha yeni bir Web uygulaması Ara sunucusu (WAP) sunucusu olarak. Bu yapılandırma:
  - Cihazların bir İnternet bağlantısını kullanarak sertifikaları almasını sağlar.
  - Cihazlar sertifikaları almak ve yenilemek için İnternet üzerinden bağlanıyorsa güvenlik açısından önerilir.
  
- **Azure AD uygulama proxy'si** (isteğe bağlı): Azure AD uygulama proxy'si, NDES sunucusunun Internet'e yayımlamak için ayrılmış bir Web uygulaması Ara sunucusu (WAP) sunucusu yerine kullanılabilir. Daha fazla bilgi için bkz. [Şirket içi uygulamalara güvenli uzaktan erişim sağlama](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

#### <a name="additional"></a>Ek

- WAP'ı barındıran sunucular, Ağ Cihazı Kayıt Hizmeti tarafından kullanılan uzun URL'ler için destek sağlayan [bir güncelleştirmeyi yüklemelidir](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) . Bu güncelleştirmeyi [Aralık 2014 güncelleştirme paketi](http://support.microsoft.com/kb/3013769)ile birlikte veya [KB3011135](http://support.microsoft.com/kb/3011135)güncelleştirmesinden tek başına edinebilirsiniz.
- WAP sunucusunda dış istemcilere yayımlanan adla eşleşen bir SSL sertifikası olmalı ve NDES sunucusunda kullanılan SSL sertifikasına güvenilmelidir. Bu sertifikalar, WAP sunucusunun istemcilerden gelen SSL bağlantıyı sonlandırmasına ve NDES sunucusuna yeni bir SSL bağlantı oluşturmasına imkan sağlar.

Daha fazla bilgi için bkz. [WAP için sertifikaları planlama](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) ve [WAP sunucuları hakkında genel bilgiler](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

### <a name="network-requirements"></a>Ağ gereksinimleri

WAP veya Azure AD Uygulama Proxy’si gibi ters bir proxy kullanmazsanız, bağlantı noktası 443’te İnternet’teki tüm konaklardan/IP adreslerinden NDES sunucusuna TCP trafiğine izin verin.

NDES sunucusu ve desteklenen herhangi bir altyapı arasında gereken tüm bağlantı noktalarına ve protokollere izin verin. Örneğin NDES sunucusunun CA, DNS sunucuları, Configuration Manager sunucuları, etki alanı denetleyicileri ve muhtemelen ortamınızdaki diğer hizmetler ile iletişim kurması gerekiyor.

NDES sunucusunun [Azure AD uygulama ara sunucusu](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Erişim Ara Sunucusu](https://technet.microsoft.com/library/dn584107.aspx) veya üçüncü taraf bir ara sunucu gibi ters bir ara sunucu aracılığıyla yayımlanmasını özellikle öneririz.

### <a name="certificates-and-templates"></a>Sertifikalar ve şablonlar  

|Nesne|Ayrıntılar|
|----------|-----------|
|**Sertifika Şablonu**|Bu şablonu sertifika veren CA'nız üzerinde yapılandırın.|
|**İstemci kimlik doğrulama sertifikası**|Sertifika veren CA'nızdan veya genel CA'dan istenen bu sertifikayı NDES Sunucusu'na yüklersiniz.|
|**Sunucu kimlik doğrulama sertifikası**|Sertifika veren CA'nızdan veya genel CA'dan istenen bu SSL sertifikasını NDES Sunucusu'ndaki IIS'de yüklersiniz ve bağlarsınız. Sertifikada istemci ve sunucu kimlik doğrulaması anahtar kullanımları ayarlıysa (**Gelişmiş Anahtar Kullanımları**) aynı sertifikayı kullanabilirsiniz.|
|**Güvenilen Kök CA sertifika**|Bu sertifikayı, kök CA’sından veya kök CA’sına güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarırsınız. Ardından, kullanıcılar, cihazlar veya her iki kullanarak güvenilen CA sertifika profili atayın.<br /><b>Not:<b />bir SCEP sertifika profili atandığında, aynı kullanıcı veya cihaz grubuna SCEP sertifika profilinde başvurulan güvenilen kök sertifika profilini atadığınızdan emin olun.<br /><br />İşletim sistemi platformu başına tek bir Güvenilen Kök CA sertifika kullanırsınız ve bu sertifikayı oluşturduğunuz her Güvenilen Kök Sertifika profili ile ilişkilendirirsiniz.<br /><br />Gerektiğinde ek Güvenilen Kök CA sertifikaları kullanabilirsiniz. Örneğin, Wi-Fi erişim noktalarınız için sunucu kimlik doğrulama sertifikalarını imzalayan bir CA'ya güven sağlamak için bunu yapabilirsiniz.|

### <a name="accounts"></a>Hesaplar

|Ad|Ayrıntılar|
|--------|-----------|
|**NDES hizmet hesabı**|NDES Hizmet hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı girin. |

## <a name="configure-your-infrastructure"></a>Altyapınızı yapılandırın
Sertifika profillerini yapılandırabilmek için önce aşağıdaki adımları tamamlayın. Bu adımlar, Windows Server 2012 R2 veya üzeri sürümler ile Active Directory Sertifika Hizmetleri (ADCS) bilgisi gerektirir:

#### <a name="step-1---create-an-ndes-service-account"></a>Adım 1 - NDES hizmet hesabı oluşturma

NDES hizmet hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı oluşturun. NDES’i yükleyip yapılandırmadan önce, sertifika veren CA’da şablonları yapılandırırken bu hesabı girersiniz. Kullanıcının **Yerel Olarak Oturum Açma**, **Hizmet Olarak Oturum Açma** ve **Toplu iş olarak oturum açma** varsayılan haklarına sahip olduğundan emin olun. Bazı kuruluşların söz konusu hakları devre dışı bırakan sağlamlaştırma ilkeleri vardır.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Adım 2 - Sertifika yetkilisinde sertifika şablonlarını yapılandırma
Bu adımda şunları yapacaksınız:

- NDES için bir sertifika şablonu yapılandırma
- NDES için oluşturulan sertifika şablonunu yayımlama

##### <a name="configure-the-certification-authority"></a>Sertifika yetkilisini yapılandırma

1. Kuruluş yöneticisi olarak oturum açın.

2. Sertifika veren CA’da yeni bir özel şablon oluşturmak için Sertifika Şablonları ek bileşenini kullanın. Veya mevcut bir şablonu kopyalayıp ardından bu şablonu (Kullanıcı şablonu gibi) NDES ile kullanım için güncelleştirin.

   >[!NOTE]
   > NDES sertifika şablonunun (Windows 2003 ile uyumlu) bir v2 Sertifika Şablonu'nu temel alması gerekir.

   Şablonun aşağıdaki yapılandırmalara sahip olması gerekir:

   - **Genel**’de:
   
       - **Active Directory’de sertifika yayımla** özelliğinin seçili **olmadığını** onaylayın.
       - Şablon için kolay bir **Şablon görünen adı** girin.

   - **Konu Adı**’nda **İstekte sağla**’yı seçin. (Güvenlik, NDES için Intune ilke modülü tarafından zorunlu tutulur).

   - **Uzantılar**’da **Uygulama İlkeleri Açıklaması**’nın **İstemci Kimlik Doğrulaması**’nı içerdiğini doğrulayın.

     > [!IMPORTANT]
     > iOS ve macOS sertifika şablonları için **Uzantılar** sekmesinde **Anahtar Kullanımı**’nı düzenleyin ve **İmza kaynağın delilidir** öğesinin seçili olmadığını doğrulayın.

   - **Güvenlik**’te NDES hizmet hesabını ekleyin ve bu hesaba şablon üzerinde **Kaydetme** izinleri verin. SCEP profillerini oluşturan Intune yöneticilerinin, SCEP profillerini oluştururken şablona göz atabilmeleri için **Okuma** hakları olmalıdır.

     > [!NOTE]
     > Sertifikaları iptal etmek için, NDES hizmet hesabının sertifika profili tarafından kullanılan her sertifika şablonu üzerinde *Sertifikaları Yayımlama ve Yönetme* hakları olmalıdır.

3. Şablonun **Genel** sekmesindeki **Geçerlilik süresi** 'ni gözden geçirin. Varsayılan olarak, Intune şablonda yapılandırılan değeri kullanır. Ancak CA’yı, istekte bulunan kişinin farklı bir değer girmesine izin verecek şekilde yapılandırabilirsiniz ve bu değeri daha sonra Intune yönetim konsolundan ayarlayabilirsiniz. Her zaman şablondaki değeri kullanmak istiyorsanız bu adımın geri kalanını atlayın.

   > [!IMPORTANT]
   > iOS ve macOS, yaptığınız diğer yapılandırmalar ne olursa olsun, her zaman şablonda ayarlanan değeri kullanır.

Örnek şablon yapılandırması:

![Şablon, istek işleme sekmesi](./media/scep_ndes_request_handling.png)

![Şablon, konu adı sekmesi](./media/scep_ndes_subject_name.jpg)

![Şablon, güvenlik sekmesi](./media/scep_ndes_security.jpg)

![Şablon, uzantılar sekmesi](./media/scep_ndes_extensions.jpg)

![Şablon, verme gereklilikleri sekmesi](./media/scep_ndes_issuance_reqs.jpg)

> [!IMPORTANT]
> Uygulama İlkeleri için yalnızca gerekli uygulama ilkelerini ekleyin. Seçimlerinizi güvenlik yöneticilerinizle onaylayın.

İstekte bulunan kişinin geçerlilik süresini belirlemesine izin verecek şekilde CA’yı yapılandırın:

1. CA’da aşağıdaki komutları çalıştırın:
   - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   - **net stop certsvc**
   - **net start certsvc**

2. Sertifika veren CA'da, sertifika şablonunu yayımlamak için Sertifika Yetkilisi ek bileşenini kullanın.
   **Sertifika Şablonları** düğümünü seçin, **Eylem** > **Yeni** > **Verilecek Sertifika Şablonu**’na tıklayın ve ardından 2. adımda oluşturduğunuz şablonu seçin.

3. Şablonu **Sertifika Şablonları** klasöründe görüntüleyerek yayımlandığını doğrulayın.

#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Adım 3 - NDES sunucusunda önkoşulları yapılandırma
Bu adımda şunları yapacaksınız:

- NDES'i bir Windows Server'a ekleyin ve IIS'yi NDES'i destekleyecek biçimde yapılandırın
- NDES Hizmet hesabını IIS_IUSR grubuna ekleyin
- NDES Hizmet hesabına ait hizmet asıl adını (SPN) ayarlama

1. NDES’i barındıran sunucuda bir **Kuruluş Yöneticisi** olarak oturum açın ve sonra NDES’i yüklemek için [Rol ve Özellik Ekle Sihirbazı](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11))’nı kullanın:

   1. Sihirbaz'da, AD CS Rol Hizmetleri'ne erişmek için **Active Directory Sertifika Hizmetleri** 'ni seçin. **Ağ Cihazı Kayıt Hizmeti**'ni seçin, **Sertifika Yetkilisi**'nin işaretini kaldırın ve ardından sihirbazı tamamlayın.

      > [!TIP]
      > **Yükleme ilerlemesi**’nde **Kapat**’ı işaretlemeyin. Bunun yerine, **Hedef sunucuda Active Directory Sertifika Hizmetleri’ni Yapılandır** bağlantısını seçin. Sonraki adım için kullanacağınız **AD CS Yapılandırma** sihirbazı açılır. AD CS Yapılandırması açıldıktan sonra, Rol ve Özellik Ekle sihirbazını kapatabilirsiniz.

   2. NDES sunucuya eklendiğinde, sihirbaz tarafından IIS de yüklenir. IIS’nin aşağıdaki yapılandırmalara sahip olduğunu onaylayın:

       - **Web Sunucusu** > **Güvenlik** > **İstek Filtreleme**

       - **Web Sunucusu** > **Uygulama Geliştirme** > **ASP.NET 3.5** 

            ASP.NET 3.5 yüklendiğinde .NET Framework 3.5 de yüklenir. .NET Framework 3.5'i yüklerken, hem çekirdek **.NET Framework 3.5** özelliğini hem de **HTTP Etkinleştirmesi**'ni yükleyin.

       - **Web Sunucusu** > **Uygulama Geliştirme** > **ASP.NET 4.5** 

            ASP.NET 4.5 yüklendiğinde .NET Framework 4.5 de yüklenir. .NET Framework 4.5’i yüklerken çekirdek **.NET Framework 4.5** özelliğini, **ASP.NET 4.5**’i ve **WCF Hizmetleri** > **HTTP Etkinleştirmesi** özelliğini yükleyin.

       - **Yönetim Araçları** > **IIS 6 Yönetim Uyumluluğu** > **IIS 6 Metatabanı Uyumluluğu**

       - **Yönetim Araçları** > **IIS 6 Yönetim Uyumluluğu** > **IIS 6 WMI Uyumluluğu**

       - Sunucuda, NDES hizmet hesabını yerel **IIS_IUSR** grubunun bir üyesi olarak ekleyin.

2. NDES hizmet hesabının SPN'sini ayarlamak için, yükseltilmiş bir komut istemcisinde şu komutu çalıştırın:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Örneğin, NDES Sunucunuzun adlı **Server01**, etki alanınız **Contoso.com**ve hizmet hesabını **NDESService**ise, şunu kullanın:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Adım 4 - NDES’i Intune’la kullanılacak şekilde yapılandırma
Bu adımda şunları yapacaksınız:

- NDES'i sertifika veren CA ile kullanmak için yapılandırma
- IIS'de sunucu kimlik doğrulaması (SSL) sertifikasını bağlama
- IIS'de İstek Filtrelemeyi Yapılandırma

1. NDES Sunucusunda, AD CS Yapılandırma sihirbazını açın ve aşağıdaki güncelleştirmeleri yapın:

    > [!TIP]
    > Önceki adımdaki bağlantıya tıkladıysanız bu sihirbaz zaten açıktır. Aksi takdirde, Active Directory Sertifika Hizmetleri için dağıtım sonrası yapılandırmaya erişmek için Sunucu Yöneticisi'ni açın.

   - **Rol Hizmetleri**’nde **Ağ Cihazı Kayıt Hizmeti**’ni seçin
   - **NDES için Hizmet Hesabı**’nda NDES Hizmet Hesabı’nı belirtin
   - **NDES için CA**’da **Seçin**’e tıklayın ve ardından, sertifika şablonunu yapılandırdığınız yerde sertifika veren CA’yı seçin
   - **NDES için şifreleme**’de anahtar uzunluğunu şirket gereksinimlerinizi karşılayacak şekilde ayarlayın.
   - **Onay**’da sihirbazı tamamlamak için **Yapılandır**’a tıklayın.

2. Sihirbaz tamamlandıktan sonra, NDES Sunucusu’nda aşağıdaki kayıt defteri anahtarını güncelleştirin:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Bu anahtarı güncelleştirmek için sertifika şablonunun **Amacını** belirleyin (şablonun **İstek İşleme** sekmesinde bulunur). Daha sonra, mevcut verileri 2. Adım'da belirttiğiniz sertifika şablonu adıyla (şablonun görünen adıyla değil) değiştirerek karşılık gelen kayıt defteri girdisini güncelleştirin. Aşağıdaki tabloda, sertifika şablonu amacı ile kayıt defterindeki değerler eşleştirilmiştir:

    |Sertifika şablonunun Amacı (İstek İşleme sekmesinde)|Düzenlenecek kayıt defteri değeri|SCEP profili için Intune yönetim konsolunda görünen değer|
    |---|---|---|
    |İmza|SignatureTemplate|Dijital İmza|
    |Şifreleme|EncryptionTemplate|Anahtar Şifrelemesi|
    |İmza ve şifreleme|GeneralPurposeTemplate|Anahtar Şifrelemesi<br/>Dijital İmza|

    Örneğin, sertifika şablonunuzun Amacı **Şifreleme**ise **EncryptionTemplate** değerini sertifika şablonunuzun adı olacak biçimde düzenleyin.

3. NDES sunucusu çok uzun URL’ler (sorgular) aldığından, iki kayıt defteri girdisi eklemeniz gerekir:


   |                        Konum                        |      Değer      | Type  |      Veriler       |
   |--------------------------------------------------------|-----------------|-------|-----------------|
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxFieldLength  | DWORD | 65534 (ondalık) |
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxRequestBytes | DWORD | 65534 (ondalık) |

4. IIS yöneticisinde **Varsayılan Web Sitesi** > **İstek Filtreleme** > **Özellik Ayarını Düzenle**’yi seçin. **En yüksek URL uzunluğu**’nu ve **En yüksek sorgu dizesini** aşağıda gösterildiği gibi *65534* olarak değiştirin:

    ![IIS en fazla URL ve sorgu uzunluğu](./media/SCEP_IIS_max_URL.png)

5. Sunucuyu yeniden başlatın. Değişiklikleri sonlandırmadığından **iisreset** kullanmayın.
6. konumuna gözatın `http://*FQDN*/certsrv/mscep/mscep.dll`. Şuna benzeyen bir NDES sayfası görmelisiniz:

    ![Test NDES](./media/SCEP_NDES_URL.png)

    **503 Hizmet kullanılamıyor** hatası alırsanız, olay görüntüleyicisini gözden geçirin. NDES kullanıcısı için bir hakkın eksik olması nedeniyle uygulama havuzu durdurulmuş olabilir. Bu haklar 1. Adım'da açıklanmıştır.

##### <a name="install-and-bind-certificates-on-the-ndes-server"></a>NDES Sunucusu’nda sertifika yükleme ve bağlama

1. NDES Sunucunuzda, iç CA'nızdan veya genel CA'dan bir **sunucu kimlik doğrulaması** sertifikası isteyin ve yükleyin. Ardından bu SSL sertifikasını IIS'de bağlarsınız.

    > [!TIP]
    > SSL sertifikasını IIS'de bağladıktan sonra, bir de istemci kimlik doğrulama sertifikası yükleyin. Bu sertifika, NDES Sunucusu tarafından güvenilen bir CA tarafından verilebilir. Sertifikada istemci ve sunucu kimlik doğrulaması anahtar kullanımları ayarlıysa (**Gelişmiş Anahtar Kullanımları**) aynı sertifika kullanılabilir. Bu kimlik doğrulama sertifikaları hakkında bilgi için aşağıdaki adımları gözden geçirin.

   1. Sunucu kimlik doğrulama sertifikasını aldıktan sonra **IIS Yöneticisi**’ni açın ve **Varsayılan Web Sitesi**’ni seçin. **Eylemler** bölmesinde **Bağlamalar**’a tıklayın.

   2. **Ekle**’ye tıklayın, **Tür**’ü **https** olarak ayarlayın ve sonra bağlantı noktasının **443** olduğunu doğrulayın. Tek başına Intune için yalnızca bağlantı noktası 443 desteklenir.

   3. **SSL sertifikası** için sunucu kimlik doğrulama sertifikasını girin.

      > [!NOTE]
      > NDES sunucusu tek bir ağ adresi için harici ve dahili ad kullanıyorsa, sunucu kimlik doğrulama sertifikasında şunlar olmalıdır:
      > - Harici ortak sunucu adı içeren bir **Konu Adı**
      > - Dahili sunucu adını içeren bir **Konu Alternatif Adı**

2. NDES Sunucunuzda, iç CA'nızdan ya da genel bir sertifika yetkilisinden bir **istemci kimlik doğrulaması** sertifikası isteyin ve yükleyin. Bu sertifika, her iki özelliği de içeriyorsa sunucu kimlik doğrulama sertifikası ile aynı sertifika olabilir.

    İstemci kimlik doğrulama sertifikasının aşağıdaki özelliklere sahip olması gerekir:

    - **Gelişmiş anahtar kullanımı**: Bu değeri içermelidir **istemci kimlik doğrulaması**

    - **Konu adı**: Değer (NDES sunucusu) sertifika yüklemekte sunucunun DNS adına eşit olmalıdır

##### <a name="configure-iis-request-filtering"></a>IIS istek filtrelemeyi yapılandırma

1. NDES Sunucusu’nda **IIS Yöneticisi**’ni açın, **Bağlantılar** bölmesinden **Varsayılan Web Sitesi**’ni seçin ve ardından **İstek Filtreleme**’yi açın.

2. **Özellik Ayarlarını Düzenle**’ye tıklayın ve ardından şu değerleri ayarlayın:

    - **sorgu dizesi (Bayt)** = **65534**
    - **URL uzunluğu üst sınırı (Bayt)** = **65534**

3. Aşağıdaki kayıt defteri anahtarını inceleyin:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

    Aşağıdaki değerlerin DWORD girişleri olarak ayarlandığını doğrulayın:

    - Adı: **MaxFieldLength**, ondalık bir değer ile **65534**
    - Adı: **MaxRequestBytes**, ondalık bir değer ile **65534**

4. NDES sunucusunu yeniden başlatın. Sunucu artık Sertifika Bağlayıcısı'nı desteklemeye hazırdır.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Adım 5 - Intune sertifika bağlayıcısını etkinleştirme, yükleme ve yapılandırma
Bu adımda şunları yapacaksınız:

- Intune’da NDES desteğini etkinleştirme.
- Basit Sertifika Kayıt Protokolü (NDES) rolünü barındıran sunucuda Sertifika Bağlayıcısı’nı indirin, yükleyin ve yapılandırın. Kuruluşunuzdaki NDES uygulamasının ölçeğini artırmak için istediğiniz sayıda NDES sunucusuna Microsoft Intune Sertifika Bağlayıcısı yükleyebilirsiniz.

##### <a name="download-install-and-configure-the-certificate-connector"></a>Sertifika bağlayıcısını indirme, yükleme ve yapılandırma

> [!IMPORTANT] 
> Microsoft Intune Sertifika Bağlayıcısı, ayrı bir Windows sunucusunda yüklü **olmalıdır**. Sertifika veren Sertifika Yetkilisi’ne (CA) yüklenemez. Ayrıca Ağ Cihazı Kayıt Hizmeti (NDES) rolüyle aynı sunucuda da yüklü **olmalıdır**.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz Yapılandırması** > **Sertifika Yetkilisi** > **Ekle** seçeneğini belirleyin
3. Bağlayıcı dosyasını indirip kaydedin. Bağlayıcıyı, yükleyeceğiniz sunucudan erişilebilir bir konuma kaydedin.

    ![ConnectorDownload](./media/certificates-download-connector.png)

4. İndirme tamamlandıktan sonra Ağ Cihazı Kayıt Protokolü (NDES) rolünü barındıran sunucuya gidin. Daha sonra:

    1. NDES Sertifika bağlayıcısının gerektirdiği .NET 4.5 Framework’ün yüklü olduğundan emin olun. .NET 4.5 Framework, Windows Server 2012 R2 ve daha yeni sürümlere otomatik olarak eklenir.
    2. Yükleyiciyi çalıştırın (**NDESConnectorSetup.exe**). Yükleyici, NDES ve CRP Web Hizmeti için ilke modülünü de yükler. CRP Web Hizmeti yani CertificateRegistrationSvc, IIS'de bir uygulama olarak çalışır.

    > [!NOTE]
    > Tek başına Intune için NDES yüklediğinizde, CRP hizmeti Sertifika Bağlayıcısı ile otomatik olarak yüklenir. Intune’u Configuration Manager ile kullandığınızda, Sertifika Kayıt Noktası'nı ayrı bir site sistem rolü olarak yüklersiniz.

5. Sertifika Bağlayıcısı için istemci sertifikası istendiğinde **Seç** düğmesini, ardından 4. Adım'da NDES Sunucunuza yüklediğiniz **istemci kimlik doğrulaması** sertifikasını seçin.

    İstemci kimlik doğrulaması sertifikasını seçtikten sonra, **Microsoft Intune Sertifika Bağlayıcısı için İstemci Sertifikası** yüzeyine dönersiniz. Seçtiğiniz sertifika gösterilmese de bu sertifikanın özelliklerini görüntülemek için **İleri**’ye tıklayın. **İleri**’yi ve ardından **Yükle**’yi seçin.

    > [!IMPORTANT]
    > Internet Explorer Artırılmış Güvenlik Yapılandırması, Intune Sertifika Bağlayıcısını barındıran [NDES sunucusunda devre dışı bırakılmalıdır](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx).

6. Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**’a tıklayın.

    > [!TIP]
    > Sertifika Bağlayıcısı Kullanıcı Arabirimi'ni başlatmadan sihirbazı kapatırsanız, aşağıdaki komutu çalıştırarak yeniden açabilirsiniz:
    >
    > <install_Path>\NDESConnectorUI\NDESConnectorUI.exe

7. **Sertifika Bağlayıcısı** kullanıcı arabiriminde:

    **Oturum Aç**’a tıklayın ve Intune hizmet yöneticisi kimlik bilgilerinizi veya genel yönetim izni olan bir kiracı yöneticiye ait kimlik bilgilerini girin. Oturum açtıktan sonra Intune Sertifika Bağlayıcısı Intune’dan bir sertifika indirir. Bu sertifika, bağlayıcı ve Intune arasında kimlik doğrulaması için kullanılır.

    > [!IMPORTANT]
    > Kullanıcı hesabına geçerli bir Intune lisansı atanmış olması gerekir. Kullanıcı hesabının geçerli bir Intune lisansı yoksa, NDESConnectorUI.exe başarısız olur.

    Kuruluşunuz bir ara sunucu kullanıyorsa ve NDES sunucusunun İnternet’e erişmesi için ara sunucu gerekliyse **Ara sunucu kullan**’a tıklayın. Daha sonra, bağlanmak için ara sunucu adını, bağlantı noktasını ve hesap kimlik bilgilerini girin.

    **Gelişmiş** sekmesini seçin ve ardından sertifika veren Sertifika Yetkilinizde **Sertifika Ver ve Yönet** iznine sahip olan bir hesabın kimlik bilgilerini girin. Yaptığınız değişiklikleri **uygulayın**.

    Şimdi Sertifika Bağlayıcısı kullanıcı arabirimini kapatabilirsiniz.

8. Bir komut istemi açın ve **services.msc** yazıp **Enter** tuşuna basın. **Intune Bağlayıcı Hizmeti** > **Yeniden Başlat**’a sağ tıklayın.

Hizmetin çalıştığını doğrulamak için bir tarayıcı açın ve aşağıdaki URL’yi girin. Bu URL’nin bir **403** hatası döndürmesi gerekir:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> TLS 1.2 desteği, NDES Sertifika Bağlayıcısına dahil edilmiştir. Bu nedenle NDES Sertifika bağlayıcısı yüklü olan sunucu TLS 1.2’yi destekliyorsa TLS 1.2 kullanılır. Sunucu TLS 1.2 desteklemiyorsa TLS 1.1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

## <a name="create-a-scep-certificate-profile"></a>Bir SCEP sertifika profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. SCEP sertifika profili için bir **Ad** ve **Açıklama** girin.
4. **Platform** açılan listesinde, bu SCEP sertifikası için cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
   - **Android**
   - **Android Kurumsal**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 ve üzeri**
   - **Windows 10 ve üzeri**
5. **Profil** türü açılan listesinde **SCEP sertifikası**’nı seçin.
6. Aşağıdaki ayarları girin:

   - **Sertifika türü**: Seçin **kullanıcı** kullanıcı sertifikaları için. Bilgi noktası gibi kullanıcısız cihazlar için **Cihaz**'ı seçin. **Cihaz** sertifikaları aşağıdaki platformlar için bulunur:  
     - iOS
     - Windows 8.1 ve üzeri
     - Windows 10 ve üzeri
     - Android Kurumsal

   - **Konu adı biçimi**: Nasıl Intune otomatik olarak konu adı sertifika isteğindeki seçin. Seçenekler, **Kullanıcı** ya da **Cihaz** sertifika türünü seçmenize bağlı olarak değişir. 

        **Kullanıcı sertifika türü**  

        Kullanıcının e-posta adresini konu alanına dahil edebilirsiniz. Aşağıdakilerden birini seçin:

        - **Yapılandırılmadı**
        - **Ortak ad**
        - **E-postayı içeren ortak ad**
        - **E-posta olarak ortak ad**
        - **IMEI (Uluslararası Mobil Donanım Kimliği)**
        - **Seri numarası**
        - **Özel**: Bu seçeneği belirlediğinizde bir **özel** metin kutusu da gösterilir. Bu alanı, değişkenler dahil özel bir konu adı biçimi girmek için kullanın. Özel biçim iki değişkeni destekler: **Ortak ad (CN)** ve **e-posta (E)**. **Ortak Ad (CN)** şu iki değerden biri olarak ayarlanabilir:

            - **CN={{UserName}}**: Kullanıcının kullanıcı asıl adı gibi janedoe@contoso.com
            - **CN={{AAD_Device_ID}}**: Azure Active Directory (AD) bir cihaz kaydettiğinizde atanan bir kimliği. Bu kimlik genellikle Azure AD’de kimlik doğrulamak için kullanılır.
            - **CN = {{SERIALNUMBER}}**: Genellikle bir cihazı tanımlamak için üretici tarafından kullanılan benzersiz seri numarası (SN)
            - **CN={{IMEINumber}}**: Cep telefonunu tanımlamak için kullanılan uluslararası mobil ekipman kimliği (IMEI) benzersiz numarası
            - **CN={{OnPrem_Distinguished_Name}}**: Virgül ile ayrılmış bir göreli ayırt edici ad dizisi `CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

                `{{OnPrem_Distinguished_Name}}` değişkenini kullanmak için [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak `onpremisesdistingishedname` kullanıcı özniteliğini Azure AD’nizle eşitlediğinizden emin olun.

            - **CN={{onPremisesSamAccountName}}**: Yöneticiler, Azure Active Directory'den samAccountName özniteliğini eşitlenebilmesi Azure AD kullanarak AD connect adlı bir öznitelikte `onPremisesSamAccountName`. Intune, bir sertifika verme isteği kapsamında SCEP sertifikasının konusunda bu değişkeni değiştirebilir.  samAccountName özniteliği, Windows'un önceki bir sürümünden (Windows 2000 öncesi) istemcileri ve sunucuları desteklemek için kullanılan kullanıcı oturum açma adıdır. Kullanıcı oturum açma adının biçimi: `DomainName\testUser` veya yalnızca `testUser`.

                `{{onPremisesSamAccountName}}` değişkenini kullanmak için [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak `onPremisesSamAccountName` kullanıcı özniteliğini Azure AD’nizle eşitlediğinizden emin olun.

            Bu değişkenlerin ve statik dizelerin bir veya birkaç tanesinin bir bileşimini kullanarak aşağıdaki gibi özel bir konu adı biçimi oluşturabilirsiniz:  

            **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

            Bu örnekte, CN ve E değişkenlerinin yanı sıra Kuruluş Birimi, Kuruluş, Konum, Eyalet ve Ülke değerleri için dizeler kullanan bir konu adı biçimi oluşturdunuz. [CertStrToName işlevi](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx), bu işlevi ve desteklenen dizelerini açıklar.

        **Cihaz sertifika türü**  

        **Cihaz** sertifika türünü kullandığınızda, değer için aşağıdaki cihaz sertifika değişkenlerini de kullanabilirsiniz:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Bu değişkenler, özel bir değer metin kutusuna statik metin ile eklenebilir. Örneğin ortak ad `CN = {{DeviceName}}text` olarak eklenebilir.

        > [!IMPORTANT]
        >  - Konunun statik metninde bir değişkeni çevrelemeyen küme ayraçları **{ }** bir hata olarak çözümlenir. 
        >  - Bir cihaz sertifikası değişkeni kullanırken değişkeni küme parantezleri **{ }** içine alın.
        >  - `{{FullyQualifiedDomainName}}` yalnızca Windows ve etki alanına katılmış cihazlarda kullanılır. 
        >  -  Bir cihaz sertifikası için konuda veya SAN’da IMEI, Seri Numarası ve Tam Etki Alanı Adı gibi cihaz özellikleri kullanırken bunların cihaza erişimi olan birinin kandırma amacıyla değiştirilebileceğine dikkat edin.
        >  - Belirtilen cihaz değişkenleri desteklenmiyorsa profil cihaza yüklenmez. Örneğin IMEI numarası olmayan bir cihaza atanmış SCEP profilinde konu adı olarak {{IMEI}} kullanılırsa profil yüklemesi başarısız olur. 


   - **Konu alternatif adı**: Intune otomatik olarak nasıl konu alternatif adı (SAN) değerlerini sertifika isteğinde oluşturacağını girin. Seçenekler, **Kullanıcı** ya da **Cihaz** sertifika türünü seçmenize bağlı olarak değişir. 

        **Kullanıcı sertifika türü**  

        Aşağıdaki öznitelikler bulunur:

        - E-posta adresi
        - Kullanıcı asıl adı (UPN)

            Örneğin bir kullanıcı sertifikası türü seçerseniz, konu alternatif adına kullanıcı asıl adını (UPN) ekleyebilirsiniz. İstemci sertifikası bir Ağ İlkesi Sunucusunda kimlik doğrulamak için kullanılacaksa konu alternatif adını UPN'ye ayarlayın. 

        **Cihaz sertifika türü**  

        Özelleştirebileceğiniz tablo biçimli bir metin kutusu. Aşağıdaki öznitelikler bulunur:

        - DNS

        **Cihaz** sertifika türüyle değer için aşağıdaki cihaz sertifika değişkenlerini kullanabilirsiniz:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Bu değişkenler, özel değer metin kutusuna statik metin ile eklenebilir. Örneğin DNS özniteliği `DNS name = {{AzureADDeviceId}}.domain.com` olarak eklenebilir.

        > [!IMPORTANT]
        >  - SAN'ın statik metninde küme parantezleri **{ }**, kanal simgeleri **|** ve noktalı virgüller **;** kullanılamaz. 
        >  - Bir cihaz sertifikası değişkeni kullanırken değişkeni küme parantezleri **{ }** içine alın.
        >  - `{{FullyQualifiedDomainName}}` yalnızca Windows ve etki alanına katılmış cihazlarda kullanılır. 
        >  -  Bir cihaz sertifikası için konuda veya SAN’da IMEI, Seri Numarası ve Tam Etki Alanı Adı gibi cihaz özellikleri kullanırken bunların cihaza erişimi olan birinin kandırma amacıyla değiştirilebileceğine dikkat edin.
        >  - Belirtilen cihaz değişkenleri desteklenmiyorsa profil cihaza yüklenmez. Örneğin IMEI numarası olmayan bir cihaza atanmış SCEP profilinde konu diğer adı olarak {{IMEI}} kullanılırsa profil yüklemesi başarısız olur.  

   - **Sertifika geçerlilik süresi**: Çalıştırdıysanız `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE` komutu veren bir özel bir geçerlilik süresine izin veren CA ' nın sertifikanın süresi dolmadan önce kalan süreyi girebilirsiniz.<br>Sertifika şablonundaki geçerlilik süresinden düşük bir değer girebilirsiniz ancak daha yüksek bir değer giremezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa beş yıl değerini giremezsiniz ancak bir yıl değerini girebilirsiniz. Değerin, yayımlayan sertifika yetkilisinin sertifikası için kalan geçerlilik süresinden de düşük olması gerekir. 
   - **Anahtar depolama sağlayıcısı (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10): Sertifika anahtarının depolandığı girin. Aşağıdaki değerlerden birini seçin:
     - **Varsa Güvenilir Platform Modülü (TPM) KSP'sine, aksi halde Yazılım KSP'sine kaydol**
     - **Güvenilir Platform Modülü (TPM) KSP'sine kaydol, aksi halde hata ver**
     - **Passport'a kaydet, aksi halde hata ver (Windows 10 ve üzeri)**
     - **Software KSP’ye kaydol**

   - **Anahtar kullanımı**: Sertifika için anahtar kullanımı seçeneklerini girin. Seçenekleriniz şunlardır:
     - **Anahtar şifreleme**: Yalnızca anahtar şifreli olduğunda anahtar değişimine izin verir.
     - **Dijital imza**: Yalnızca anahtarın korunmasına bir dijital imza yardımcı olduğunda anahtar değişimine izin verir.
   - **Anahtar boyutu (bit)**: Anahtarın içerdiği bit sayısını seçin
   - **Karma algoritması** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): Bu sertifika ile kullanmak için kullanılabilir karma algoritma türlerinden birini seçin. Bağlanan cihazların destekleyeceği en güçlü güvenlik düzeyini seçin.
   - **Kök sertifika**: Kök daha önce yapılandırdığınız ve kullanıcıya ve/veya cihaz atanan CA sertifika profilini seçin. Bu CA sertifikası, bu sertifika profilinde yapılandırdığınız sertifikayı veren CA'nın kök sertifikası olmalıdır. SCEP sertifikası profilinde atanan aynı gruba bu güvenilen kök sertifika profilini atama emin olun.
   - **Genişletilmiş Anahtar Kullanımı**: **Ekleme** sertifikanın değerlerini sertifikaların hedeflenen amacına. Çoğu durumda, kullanıcı veya cihazın bir sunucuya kimliğini doğrulayabilmesi için, sertifika **İstemci Kimlik Doğrulaması** gerektirir. Ancak, gerektiğinde başka herhangi bir anahtar kullanımı ekleyebilirsiniz.
   - **Kayıt Ayarları**
     - **Yenileme eşiği (%)**: Cihaz yenilenmesini sertifikasının kalan sertifika ömrünün yüzde kaç olması girin.
     - **SCEP sunucu URL'leri**: SCEP aracılığıyla sertifika verecek NDES sunucuları için bir veya daha fazla URL girin. Örneğin, aşağıdakine benzer girin `https://ndes.contoso.com/certsrv/mscep/mscep.dll`.
     - **Tamam**’ı seçin ve profilinizi **Oluşturun**.

Profil oluşturulur ve profil listesi bölmesinde görüntülenir.

## <a name="assign-the-certificate-profile"></a>Sertifika profilini atama

Gruplara sertifika profillerini atamadan önce aşağıdaki noktaları göz önünde bulundurun:

- Sertifika profillerini gruplara atadığınızda, Güvenilen CA sertifika profilinden alınan sertifika dosyası cihaza yüklenir. Cihaz, bir sertifika isteği oluşturmak için SCEP sertifika profilini kullanır.
- Sertifika profilleri, yalnızca profili oluşturduğunuzda kullandığınız platformu çalıştıran cihazlara yüklenir.
- Sertifika profillerini kullanıcı koleksiyonlarına veya cihaz koleksiyonlarına atayabilirsiniz.
- Cihaz kaydolduktan sonra cihaza hızlıca bir sertifika yayımlamak için sertifika profilini bir cihaz grubu yerine bir kullanıcı grubuna atayın. Bir cihaz grubuna atarsanız, ilkeleri almadan önce cihazın tam olarak kaydedilmesi gerekir.
- Her profili ayrı olarak atasanız da Güvenilen Kök CA’sını ve SCEP veya PKCS profilini de atamanız gerekir. Aksi takdirde SCEP veya PKCS sertifika ilkesi başarısız olur.

    > [!NOTE]
    > iOS’ta aynı sertifika profilini kullanan birden fazla kaynak profili dağıtırsanız, yönetim profilinde bu sertifikanın birden çok kopyasını görmeniz olasıdır.

Profillerin nasıl atanacağı hakkında bilgi için bkz. [cihaz profilleri atama](device-profile-assign.md).

## <a name="intune-connector-setup-verification-and-troubleshooting"></a>Intune Bağlayıcısı kurulumunu doğrulama ve sorun giderme

Sorunları gidermek ve Intune Bağlayıcısı kurulumunu doğrulamak için bkz. [Sertifika Yetkilisi betik örnekleri](https://aka.ms/intuneconnectorverificationscript)

## <a name="intune-connector-events-and-diagnostic-codes"></a>Intune Bağlayıcısı olayları ve tanılama kodları

Sürüm 6.1806.x.x’ten itibaren Intune Bağlayıcısı Hizmeti, olayları **Olay Görüntüleyicisi**’nde günlüğe kaydeder (**Uygulama ve Hizmet Günlükleri** > **Microsoft Intune Bağlayıcısı**). Bu olayları, Intune Bağlayıcısı'nın yapılandırmasındaki olası sorunları gidermenize yardımcı olması için kullanın. Bu olaylar bir işlemin başarılarını ve başarısızlıklarını günlüğe kaydeder ve ayrıca BT yöneticisinin sorun gidermesine yardımcı olmak için tanılama kodlarıyla iletilerini içerir.

### <a name="event-ids-and-descriptions"></a>Olay kimlikleri ve açıklamaları

> [!NOTE]
> Her olayın İlgili Tanılama Kodları hakkındaki ayrıntılar için, bu makaledeki **Tanılama kodları** tablosunu kullanın.

| Olay Kimliği      | Olay Adı    | Olay Açıklaması | İlgili Tanılama Kodları |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Bağlayıcı hizmeti başlatıldı | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Bağlayıcı hizmeti durduruldu | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Bağlayıcı kayıt sertifikası başarıyla yenilendi | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Bağlayıcı kayıt sertifikası yenilenemedi. Bağlayıcıyı yeniden yükleyin. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Bağlayıcı kayıt sertifikası kayıt defterinden alınamadı. Bu olayla ilgili sertifika parmak izinin olay ayrıntılarını gözden geçirin. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Olay ayrıntılarındaki tanılama bilgilerini denetleyin. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | PKCS sertifikası başarıyla verildi. Bu olayla ilgili cihaz kimliği, kullanıcı kimliği, CA adı, sertifika şablonu adı ve sertifika parmak izi gibi olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | PKCS sertifikası verilemedi. Bu olayla ilgili cihaz kimliği, kullanıcı kimliği, CA adı, sertifika şablonu adı ve sertifika parmak izi gibi olay ayrıntılarını gözden geçirin. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Sertifika başarıyla iptal edildi. Bu olayla ilgili cihaz kimliği, kullanıcı kimliği, CA adı ve sertifika seri numarası gibi olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Sertifika iptal edilemedi. Bu olayla ilgili cihaz kimliği, kullanıcı kimliği, CA adı ve sertifika seri numarası gibi olay ayrıntılarını gözden geçirin. Ek bilgi için NDES SVC Günlükleri'ne bakın.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Sertifikanın istek veya iptal verileri başarıyla karşıya yüklendi. Karşıya yükleme ayrıntıları için olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Sertifikanın istek veya iptal verileri karşıya yüklenemedi. Hatanın hangi noktada oluştuğunu saptamak için olay ayrıntıları > Karşıya Yükleme Durumu'nu gözden geçirin.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Sertifika imzalama, istemci sertifikası indirme veya sertifika iptal etme isteği başarıyla indirildi. İndirme ayrıntıları için olay ayrıntılarını gözden geçirin.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Sertifika imzalama, istemci sertifikası indirme veya sertifika iptal etme isteği indirilemedi. İndirme ayrıntıları için olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Sertifika Kayıt Noktası istemci sınamasını başarıyla doğruladı | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Sertifika Kayıt Noktası isteği tamamladı ama reddetti. Diğer ayrıntılar için tanılama koduna ve iletisine bakın. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Sertifika Kayıt Noktası istemci sınamasını doğrulayamadı. Diğer ayrıntılar için tanılama koduna ve iletisine bakın. Sınamaya karşılık gelen Cihaz Kimliği için olay iletisi ayrıntılarına bakın. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Sertifika Kayıt Noktası bildirme işlemini başarıyla bitirdi ve sertifikayı istemci cihazına gönderdi. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Sertifika Kayıt Noktası bildirme işlemini bitiremedi. İstekle ilgili bilgiler için olay iletisi ayrıntılarına bakın. NDES sunucusuyla CA arasındaki bağlantıyı doğrulayın. | 0x00000000, 0x0FFFFFFF |

### <a name="diagnostic-codes"></a>Tanılama kodları

| Tanılama Kodu | Tanı Adı | Tanılama İletisi |
| -------------   | -------------   | -------------      |
| 0x00000000 | Başarılı  | Başarılı |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Sertifika yetkilisi geçerli değil veya yetkiliye ulaşılamıyor. Sertifika yetkilisinin kullanılabilir olduğunu ve sunucunuzun onunla iletişim kurabildiğini doğrulayın. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Yerel sertifika deposunda Symantec Client Auth sertifikası bulunamadı. Daha fazla bilgi için [Symantec kayıt yetkilendirme sertifikası yükleme](https://docs.microsoft.com/intune/certificates-symantec-configure#install-the-symantec-registration-authorization-certificate) makalesine bakın.  |
| 0x00000402 | RevokeCert_AccessDenied  | Belirtilen hesabın CA'dan sertifika iptal etme izinleri yok. Veren CA'yı saptamak için olay iletisi ayrıntılarında CA Adı alanına bakın.  |
| 0x00000403 | CertThumbprint_NotFound  | Girişinizle eşleşen bir sertifika bulunamadı. Sertifika bağlayıcısının kaydını yapın ve yeniden deneyin. |
| 0x00000404 | Certificate_NotFound  | Sağlanan girişle eşleşen bir sertifika bulunamadı. Sertifika bağlayıcısının kaydını yeniden yapın ve bir kez daha deneyin. |
| 0x00000405 | Certificate_Expired  | Sertifikanın süresi doldu. Sertifikayı yenilemek için sertifika bağlayıcısının kaydını yeniden yapın ve bir kez daha deneyin. |
| 0x00000408 | CRPSCEPCert_NotFound  | CRP Şifreleme sertifikası bulunamadı. NDES ve Intune Connector'ın düzgün kurulduğunu doğrulayın. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | İmzalama sertifikası alınamadı. Intune Bağlayıcı Hizmeti'nin düzgün yapılandırıldığını ve Intune Bağlayıcı Hizmeti'nin çalıştığını doğrulayın. Ayrıca sertifika indirme olaylarının başarılı olduğunu da doğrulayın. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | SCEP sınama isteği seri durumdan çıkarılamadı. NDES ile Intune Connector'ın düzgün kurulduğunu doğrulayın. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Sertifika sınamasının süresi dolduğundan istek reddedildi. İstemci cihazı yönetim sunucusundan yeni bir sınama aldıktan sonra bir kez daha deneyebilir. |
| 0x0FFFFFFFF | Unknown_Error  | Bir sunucu tarafı hatası oluştuğundan isteğinizi tamamlayamadık. Lütfen yeniden deneyin. |

## <a name="next-steps"></a>Sonraki adımlar

- [PKCS sertifikalarını kullanmak](certficates-pfx-configure.md), veya [Symantec PKI manager web hizmeti PKCS sertifikaları verme](certificates-symantec-configure.md)
- [Intune ile SCEP kullanılacak bir 3. taraf CA Ekle](certificate-authority-add-scep-overview.md)
- Ek Yardım için kullanmak [sorun giderme SCEP sertifika profili dağıtımı Microsoft Intune](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune) Kılavuzu.