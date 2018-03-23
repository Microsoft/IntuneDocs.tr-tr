---
title: Microsoft Intune ile SCEP sertifikalarını yapılandırma ve yönetme
description: Altyapınızın nasıl yapılandırılacağı ve ardından Microsoft Intune ile Intune Basit Sertifika Kayıt Protokolü (SCEP) sertifika profillerinin nasıl oluşturulup atanacağını öğrenin.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88109f1dc4543a5c71f36378fddb110c03afa08f
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2018
---
# <a name="configure-and-manage-scep-certificates-with-microsoft-intune"></a>Microsoft Intune ile SCEP sertifikalarını yapılandırma ve yönetme
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konuda, altyapınızın nasıl yapılandırılacağı ve ardından Intune ile Basit Sertifika Kayıt Protokolü (SCEP) sertifika profillerinin nasıl oluşturulup atanacağı gösterilir.

## <a name="configure-on-premises-infrastructure"></a>Şirket içi altyapıyı yapılandırma

-    **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucular (Web Uygulaması Ara Sunucusu hariç), Active Directory etki alanınıza katılmalıdır.

-  **Sertifika Yetkilisi** (CA): Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. Ayrıntılar için bkz. [Sertifika Yetkilisi'ni yükleme](http://technet.microsoft.com/library/jj125375.aspx).
    CA'nız Windows Server 2008 R2 çalıştırıyorsa, [KB2483564 ile gelen düzeltmeyi yüklemeniz](http://support.microsoft.com/kb/2483564/)gerekir.

-  **NDES Sunucusu**: Windows Server 2012 R2 veya üstünü çalıştıran bir sunucuya Ağ Cihazı Kayıt Hizmeti’ni (NDES) kurmalısınız. Intune, Kuruluş CA ile aynı sunucuda çalıştırılan NDES’nin kullanımını desteklemez. Windows Server 2012 R2’yi Ağ Cihazı Kayıt Hizmeti’ni barındıracak şekilde yapılandırma yönergeleri için bkz. [Ağ Cihazı Kayıt Hizmeti Kılavuzu](http://technet.microsoft.com/library/hh831498.aspx).
NDES sunucusu CA’yı barındıran etki alanına katılmış olmalı ve CA ile aynı sunucuda yer almamalıdır. NDES sunucusunu ayrı bir ormanda, yalıtılmış ağda veya iç etki alanında dağıtma hakkında daha fazla bilgi, [Ağ Cihazı Kayıt Hizmeti ile İlke Modülü Kullanma](https://technet.microsoft.com/library/dn473016.aspx) başlığı altında bulunabilir.

-  **Microsoft Intune Sertifika Bağlayıcısı**: **Sertifika Bağlayıcısı** yükleyicisini (**ndesconnectorssetup.exe**) indirmek için Azure portalını kullanın. Ardından, Sertifika Bağlayıcısı’nı yüklemeniz gereken Basit Sertifika Kayıt Protokolü (NDES) rolünü barındıran sunucuda **ndesconnectorssetup.exe** dosyasını çalıştırabilirsiniz. 
-  **Web Uygulaması Ara Sunucusu** (isteğe bağlı): Web Uygulaması Ara Sunucusu (WAP) olarak Windows Server 2012 R2 veya üzerini çalıştıran bir sunucu kullanın. Bu yapılandırma:
    -  Cihazların bir İnternet bağlantısını kullanarak sertifikaları almasını sağlar.
    -  Cihazlar sertifikaları almak ve yenilemek için İnternet üzerinden bağlanıyorsa güvenlik açısından önerilir.

 > [!NOTE]           
> -    WAP'ı barındıran sunucular, Ağ Cihazı Kayıt Hizmeti tarafından kullanılan uzun URL'ler için destek sağlayan [bir güncelleştirmeyi yüklemelidir](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) . Bu güncelleştirmeyi [Aralık 2014 güncelleştirme paketi](http://support.microsoft.com/kb/3013769)ile birlikte veya [KB3011135](http://support.microsoft.com/kb/3011135)güncelleştirmesinden tek başına edinebilirsiniz.
>-  Ayrıca, WAP’yi barındıran sunucuda, dış istemcilere yayımlanan adla eşleşen bir SSL sertifikası olmalı ve NDES sunucusunda kullanılan SSL sertifikasına güvenilmelidir. Bu sertifikalar, WAP sunucusunun istemcilerden gelen SSL bağlantıyı sonlandırmasına ve NDES sunucusuna yeni bir SSL bağlantı oluşturmasına imkan sağlar.
    WAP sertifikaları hakkında bilgi için, [Web Uygulaması Ara Sunucusu Kullanarak Uygulama Yayınlamayı Planlama](https://technet.microsoft.com/library/dn383650.aspx) konusunun **Sertifikaları planlama** bölümüne bakın. WAP sunucuları hakkında genel bilgi için bkz. [Web Uygulaması Ara Sunucusu ile çalışma](http://technet.microsoft.com/library/dn584113.aspx).|

### <a name="network-requirements"></a>Ağ gereksinimleri

İnternet’ten çevre ağına, İnternet’te tüm konaklardan/IP adreslerinden NDES sunucusuna bağlantı noktası 443’e izin verin.

Çevre ağından güvenilen ağa, etki alanına katılmış NDES sunucusunda etki alanı erişimi için gereken tüm bağlantı noktalarına ve protokollere izin verin. NDES sunucusunun sertifika sunucularına, DNS sunucularına, Configuration Manager sunucularına ve etki alanı denetleyicilerine erişimi olmalıdır.

NDES sunucusunun [Azure AD uygulama proxy’si](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Erişim Proxy](https://technet.microsoft.com/library/dn584107.aspx)’si veya üçüncü taraf bir proxy gibi bir proxy aracılığıyla yayımlanmasını öneririz.


### <a name="certificates-and-templates"></a>Sertifikalar ve şablonlar

|Nesne|Ayrıntılar|
|----------|-----------|
|**Sertifika Şablonu**|Bu şablonu sertifika veren CA'nız üzerinde yapılandırın.|
|**İstemci kimlik doğrulama sertifikası**|Sertifika veren CA'nızdan veya genel CA'dan istenen bu sertifikayı NDES Sunucusu'na yüklersiniz.|
|**Sunucu kimlik doğrulama sertifikası**|Sertifika veren CA'nızdan veya genel CA'dan istenen bu SSL sertifikasını NDES Sunucusu'ndaki IIS'de yüklersiniz ve bağlarsınız.|
|**Güvenilen Kök CA sertifika**|Bu sertifikayı kök CA'dan veya kök CA’ya güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarabilir ve Güvenilen CA sertifika profilini kullanarak cihazlara atayabilirsiniz.<br /><br />İşletim sistemi platformu başına tek bir Güvenilen Kök CA sertifika kullanırsınız ve bu sertifikayı oluşturduğunuz her Güvenilen Kök Sertifika profili ile ilişkilendirirsiniz.<br /><br />Gerektiğinde ek Güvenilen Kök CA sertifikaları kullanabilirsiniz. Örneğin, Wi-Fi erişim noktalarınız için sunucu kimlik doğrulama sertifikalarını imzalayan bir CA'ya güven sağlamak için bunu yapabilirsiniz.|

### <a name="accounts"></a>Hesaplar

|Ad|Ayrıntılar|
|--------|-----------|
|**NDES hizmet hesabı**|NDES Hizmet hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı belirtin.|

## <a name="configure-your-infrastructure"></a>Altyapınızı yapılandırın
Sertifika profillerini yapılandırmadan önce Windows Server 2012 R2 ve Active Directory Sertifika Hizmetleri (ADCS) bilgisi gerektiren aşağıdaki görevleri tamamlamanız gerekir:

**Adım 1**: NDES hizmet hesabı oluşturma

**Adım 2**: Sertifika yetkilisinde sertifika şablonlarını yapılandırma

**Adım 3**: NDES sunucusunda önkoşulları yapılandırma

**Adım 4**: NDES’i Intune’la kullanılacak şekilde yapılandırma

**Adım 5**: Intune Sertifika Bağlayıcısı'nı etkinleştirme, yükleme ve yapılandırma

#### <a name="step-1---create-an-ndes-service-account"></a>Adım 1 - NDES hizmet hesabı oluşturma

NDES hizmet hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı oluşturun. NDES'i yükleyip yapılandırmadan önce sertifika veren CA üstünde şablonları yapılandırırken bu hesabı belirtirsiniz. Kullanıcının **Yerel Olarak Oturum Açma**, **Hizmet Olarak Oturum Açma** ve **Toplu iş olarak oturum açma** varsayılan haklarına sahip olduğundan emin olun. Bazı kuruluşların söz konusu hakları devre dışı bırakan sağlamlaştırma ilkeleri vardır.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Adım 2 - Sertifika yetkilisinde sertifika şablonlarını yapılandırma
Bu görevde şunları yapacaksınız:

-   NDES için bir sertifika şablonu yapılandırma

-   NDES için oluşturulan sertifika şablonunu yayımlama

##### <a name="to-configure-the-certification-authority"></a>Sertifika yetkilisini yapılandırmak için

1.  Kuruluş yöneticisi olarak oturum açın.

2.  Sertifika veren CA'da, Sertifika Şablonları ek bileşenini kullanarak yeni bir özel şablon oluşturun veya var olan bir şablonunu kopyalayın ve ardından, var olan bir şablonu (Kullanıcı şablonu gibi) NDES ile kullanılmak üzere düzenleyin.

    >[!NOTE]
    > NDES sertifika şablonunun (Windows 2003 ile uyumlu) bir v2 Sertifika Şablonu'nu temel alması gerekir.

    Şablonun aşağıdaki yapılandırmalara sahip olması gerekir:

    -   Şablon için kolay bir **Şablon görünen adı** belirtin.

    -   **Konu Adı** sekmesinde, **İstekte sağla**'yı seçin. (Güvenlik, NDES için Intune ilke modülü tarafından zorunlu tutulur).

    -   **Uzantılar** sekmesinde, **Uygulama İlkeleri Açıklaması** 'nın **İstemci Kimlik Doğrulaması**'nı içerdiğinden emin olun.

        > [!IMPORTANT]
        > iOS ve macOS sertifika şablonları için, **Uzantılar** sekmesinde **Anahtar Kullanımı**'nı düzenleyin ve **İmza kaynağın delilidir** öğesinin seçili olmadığından emin olun.

    -   **Güvenlik** sekmesinde, NDES hizmet hesabını ekleyin ve bu hesaba şablon üzerinde **Kaydetme** izinleri verin. SCEP profillerini oluşturan Intune yöneticilerinin, SCEP profillerini oluştururken şablona göz atabilmeleri için **Okuma** hakları olmalıdır.

    > [!NOTE]
    > Sertifikaları iptal etmek için, NDES hizmet hesabının sertifika profili tarafından kullanılan her sertifika şablonu üzerinde *Sertifikaları Yayımlama ve Yönetme* hakları olmalıdır.

3.  Şablonun **Genel** sekmesindeki **Geçerlilik süresi** 'ni gözden geçirin. Varsayılan olarak, Intune şablonda yapılandırılan değeri kullanır. Ancak, CA'yı istekte bulunan kişinin farklı bir değer belirtmesine izin verecek şekilde yapılandırma seçeneğiniz vardır ve bu değeri Intune yönetim konsolundan ayarlayabilirsiniz. Her zaman şablondaki değeri kullanmak istiyorsanız, bu adımın geri kalanını atlayın.

    > [!IMPORTANT]
    > iOS ve macOS, yaptığınız diğer yapılandırmalar ne olursa olsun, her zaman şablonda ayarlanan değeri kullanır.

Burada, örnek şablon yapılandırmasının ekran görüntüleri verilmiştir.

![Şablon, istek işleme sekmesi](.\media\scep_ndes_request_handling.png)

![Şablon, konu adı sekmesi](.\media\scep_ndes_subject_name.jpg)

![Şablon, güvenlik sekmesi](.\media\scep_ndes_security.jpg)

![Şablon, uzantılar sekmesi](.\media\scep_ndes_extensions.jpg)

![Şablon, verme gereklilikleri sekmesi](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Uygulama İlkeleri için yalnızca gerekli uygulama ilkelerini ekleyin. Seçimlerinizi güvenlik yöneticilerinizle onaylayın.



CA'yı istekte bulunan kişinin geçerlilik süresini belirlemesine izin verecek şekilde yapılandırmak için:

1. CA'da aşağıdaki komutları çalıştırın:
    - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
    - **net stop certsvc**
    - **net start certsvc**
2. Sertifika veren CA'da, sertifika şablonunu yayımlamak için Sertifika Yetkilisi ek bileşenini kullanın.
    **Sertifika Şablonları** düğümünü seçin, **Eylem**-&gt; **Yeni** &gt; **Verilecek Sertifika Şablonu** öğesine tıklayın ve ardından 2. adımda oluşturduğunuz şablonu seçin.
3. Şablonu **Sertifika Şablonları** klasöründe görüntüleyerek yayımlandığını doğrulayın.


#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Adım 3 - NDES sunucusunda önkoşulları yapılandırma
Bu görevde yapacaklarınız:

-   NDES'i bir Windows Server'a ekleyin ve IIS'yi NDES'i destekleyecek biçimde yapılandırın

-   NDES Hizmet hesabını IIS_IUSR grubuna ekleyin

-   NDES hizmet hesabı SPN'yi ayarlayın




   1.  NDES'i barındıran sunucuda bir **Kuruluş Yöneticisi** olarak oturum açın ve sonra NDES'i yüklemek için [Rol ve Özellik Ekle Sihirbazı](https://technet.microsoft.com/library/hh831809.aspx)'nı kullanın:

    1.  Sihirbaz'da, AD CS Rol Hizmetleri'ne erişmek için **Active Directory Sertifika Hizmetleri** 'ni seçin. **Ağ Cihazı Kayıt Hizmeti**'ni seçin, **Sertifika Yetkilisi**'nin işaretini kaldırın ve ardından sihirbazı tamamlayın.

        > [!TIP]
        > Sihirbazın **Kurulum ilerleme durumu** sayfasında **Kapat**'a tıklamayın. Bunun yerine, **Hedef sunucuda Active Directory Sertifika Hizmetleri'ni Yapılandır**bağlantısına tıklayın. Bu, sonraki görev için kullanacağınız **AD CS Yapılandırma** sihirbazını açar. AD CS Yapılandırması açıldıktan sonra, Rol ve Özellik Ekle sihirbazını kapatabilirsiniz.

    2.  NDES sunucuya eklendiğinde, sihirbaz tarafından IIS de yüklenir. IIS'nin aşağıdaki yapılandırmalara sahip olduğundan emin olun:

        -   **Web Sunucusu** &gt; **Güvenlik** &gt; **İstek Filtreleme**

        -   **Web Sunucusu** &gt; **Uygulama Geliştirme** &gt; **ASP.NET 3.5**. ASP.NET 3.5 yüklendiğinde .NET Framework 3.5 de yüklenir. .NET Framework 3.5'i yüklerken, hem çekirdek **.NET Framework 3.5** özelliğini hem de **HTTP Etkinleştirmesi**'ni yükleyin.

        -   **Web Sunucusu** &gt; **Uygulama Geliştirme** &gt; **ASP.NET 4.5**. ASP.NET 4.5 yüklendiğinde .NET Framework 4.5 de yüklenir. .NET Framework 4.5'i yüklerken, çekirdek **.NET Framework 4.5** özelliğini, **ASP.NET 4.5**'i ve **WCF Hizmetleri** &gt; **HTTP Etkinleştirmesi** özelliğini yükleyin.

        -   **Yönetim Araçları** &gt; **IIS 6 Yönetim Uyumluluğu** &gt; **IIS 6 Metatabanı Uyumluluğu**

        -   **Yönetim Araçları** &gt; **IIS 6 Yönetim Uyumluluğu** &gt; **IIS 6 WMI Uyumluluğu**

  2.  Sunucuda, NDES hizmet hesabını **IIS_IUSR** grubunun bir üyesi olarak ekleyin.

   3.  NDES hizmet hesabının SPN'sini ayarlamak için, yükseltilmiş bir komut istemcisinde şu komutu çalıştırın:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Örneğin, NDES Sunucunuzun adlı **Server01**, etki alanınız **Contoso.com**ve hizmet hesabını **NDESService**ise, şunu kullanın:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Adım 4 - NDES’i Intune’la kullanılacak şekilde yapılandırma
Bu görevde şunları yapacaksınız:

-   NDES'i sertifika veren CA ile kullanmak için yapılandırma

-   IIS'de sunucu kimlik doğrulaması (SSL) sertifikasını bağlama

-   IIS'de İstek Filtrelemeyi Yapılandırma


1.  NDES Sunucusunda, AD CS Yapılandırma sihirbazını açın ve aşağıdaki yapılandırmaları yapın:

    > [!TIP]
    > Önceki görevde bulunan bağlantıya tıkladıysanız bu sihirbaz zaten açıktır. Aksi takdirde, Active Directory Sertifika Hizmetleri için dağıtım sonrası yapılandırmaya erişmek için Sunucu Yöneticisi'ni açın.

    -   **Rol Hizmetleri** Sayfasında, **Ağ Cihazı Kayıt Hizmeti**'ni seçin.

    -   **NDES için Hizmet Hesabı** sayfasında, NDES Hizmet Hesabı'nı belirtin.

    -   **NDES için CA** sayfasında, **Seç**'e tıklayın ve ardından, sertifika şablonunu yapılandırdığınız yerde sertifika veren CA'yı seçin.

    -   **NDES için şifreleme** sayfasında, anahtar uzunluğunu şirket gereksinimlerinizi karşılayacak şekilde ayarlayın.

    **Onay** sayfasında, sihirbazı tamamlamak için **Yapılandır** 'a tıklayın.

2.  Sihirbaz tamamlandıktan sonra, NDES Sunucusu'nda aşağıdaki kayıt defteri anahtarını düzenleyin:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Bu anahtarı düzenlemek için sertifika şablonunun **Amaç** değerini, anahtarın **İstek İşleme** sekmesinde bulunan değerle tanımlayın ve ardından, kayıt defterindeki mevcut verileri sertifika şablonunun Görev 1'de belirttiğiniz adıyla (şablonun görünen adı değil) değiştirerek kayıt defterinde ilgili girişi düzenleyin. Aşağıdaki tabloda, sertifika şablonu amacı ile kayıt defterindeki değerler eşleştirilmiştir:

    |Sertifika şablonunun Amacı (İstek İşleme sekmesinde)|Düzenlenecek kayıt defteri değeri|SCEP profili için Intune yönetim konsolunda görünen değer|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |İmza|SignatureTemplate|Dijital İmza|
    |Şifreleme|EncryptionTemplate|Anahtar Şifrelemesi|
    |İmza ve şifreleme|GeneralPurposeTemplate|Anahtar Şifrelemesi<br /><br />Dijital İmza|
    Örneğin, sertifika şablonunuzun Amacı **Şifreleme**ise **EncryptionTemplate** değerini sertifika şablonunuzun adı olacak biçimde düzenleyin.

3. NDES sunucusu çok uzun URL’ler (sorgular) aldığından, iki kayıt defteri girdisini eklemeniz gerekir:

    |Konum|Değer|Tür|Veri|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (ondalık)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (ondalık)|


4. IIS yöneticisinde, **Varsayılan Web Sitesi** -> **İstek Filtreleme** -> **Özellik Ayarını Düzenle**’yi seçin ve **En fazla URL uzunluğu** ve **En fazla sorgu dizesi** değerlerini gösterildiği gibi *65534* olarak değiştirin.

    ![IIS en fazla URL ve sorgu uzunluğu](.\media\SCEP_IIS_max_URL.png)

5.  Sunucuyu yeniden başlatın. Sunucuda **iisreset** komutunu çalıştırmak, bu değişiklikleri sonlandırmak için yeterli değildir.
6. Http://*FQDN*/certsrv/mscep/mscep.dll adresine göz atın. Buna benzeyen bir NDES sayfası görmelisiniz:

    ![Test NDES](.\media\SCEP_NDES_URL.png)

    **503 Hizmet kullanılamıyor** hatası alırsanız, olay görüntüleyicisini gözden geçirin. NDES kullanıcısı için bir hakkın eksik olması nedeniyle uygulama havuzu durdurulmuş olabilir. Bu haklar Görev 1'de açıklanmıştır.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>NDES Sunucusu'nda sertifikaları yüklemek ve bağlamak için

1.  NDES Sunucunuzda, iç CA'nızdan veya genel CA'dan bir **sunucu kimlik doğrulaması** sertifikası isteyin ve yükleyin. Ardından bu SSL sertifikasını IIS'de bağlarsınız.

    > [!TIP]
    > SSL sertifikasını IIS'de bağladıktan sonra, bir de istemci kimlik doğrulama sertifikası yükleyin. Bu sertifika, NDES Sunucusu tarafından güvenilen bir CA tarafından verilebilir. En iyi yöntem olmasa da, sertifika her iki Gelişmiş Anahtar Kullanımı (EKU) özelliğine de sahip olduğu sürece, aynı sertifikayı hem sunucu hem de istemci kimlik doğrulaması için kullanabilirsiniz. Bu kimlik doğrulama sertifikaları hakkında bilgi için aşağıdaki adımları gözden geçirin.

    1.  Sunucu kimlik doğrulama sertifikasını edindikten sonra **IIS Yöneticisi**'ni açın, **Bağlantılar** bölmesinden **Varsayılan Web Sitesi** 'ni seçin ve ardından, **Eylemler** bölmesinden **Bağlamalar** 'a tıklayın.

    2.  **Ekle**'ye tıklayın, **Tür** 'ü **https**olarak ayarlayın ve sonra bağlantı noktasının **443**olduğundan emin olun. (Tek başına Intune için yalnızca bağlantı noktası 443 desteklenir.)

    3.  **SSL sertifikası**için sunucu kimlik doğrulama sertifikasını belirtin.

        > [!NOTE]
        > NDES sunucusu tek bir ağ adresi için hem iç hem de dış ad kullanıyorsa, sunucu kimlik doğrulama sertifikasının bir dış genel sunucu adına sahip bir **Konu Adı** ve iç sunucu adını içeren bir **Konu Diğer Adı** olmalıdır.

2.  NDES Sunucunuzda, iç CA'nızdan ya da genel bir sertifika yetkilisinden bir **istemci kimlik doğrulaması** sertifikası isteyin ve yükleyin. Bu sertifika, her iki özelliği de içeriyorsa sunucu kimlik doğrulama sertifikası ile aynı sertifika olabilir.

    İstemci kimlik doğrulama sertifikasının aşağıdaki özelliklere sahip olması gerekir:

    **Gelişmiş Anahtar Kullanımı** - Bu, **İstemci Kimlik Doğrulaması**'nı içermelidir.

    **Konu Adı** - Bu, sertifikayı yüklediğiniz sunucunun (NDES Sunucusu) DNS adına eşit olmalıdır.

##### <a name="to-configure-iis-request-filtering"></a>IIS istek filtrelemeyi yapılandırmak için

1.  NDES Sunucusu'nda **IIS Yöneticisi**'ni açın, **Bağlantılar** bölmesinden **Varsayılan Web Sitesi** 'ni seçin ve ardından **İstek Filtreleme**'yi açın.

2.  **Özellik Ayarlarını Düzenle**'ye tıklayın ve ardından şu değerleri ayarlayın:

    **sorgu dizesi (Bayt)** = **65534**

    **URL uzunluğu üst sınırı (Bayt)** = **65534**

3.  Aşağıdaki kayıt defteri anahtarını inceleyin:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Aşağıdaki değerlerin DWORD girişleri olarak ayarlandığından emin olun:

    Ad: **MaxFieldLength**, **65534**'ün ondalık bir değeri ile

    Ad: **MaxRequestBytes**, **65534**'ün ondalık bir değeri ile

4. NDES sunucusunu yeniden başlatın. Sunucu artık Sertifika Bağlayıcısı'nı desteklemeye hazırdır.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Adım 5 - Intune sertifika bağlayıcısını etkinleştirme, yükleme ve yapılandırma
Bu görevde şunları yapacaksınız:

- Intune’da NDES desteğini etkinleştirme.
- Basit Sertifika Kayıt Protokolü (NDES) rolünü barındıran sunucuda Sertifika Bağlayıcısı’nı indirin, yükleyin ve yapılandırın. Kuruluşunuzdaki NDES uygulamasının ölçeklenebilirliğini artırmak için istediğiniz sayıda NDES sunucusuna Microsoft Intune Sertifika Bağlayıcısı yükleyebilirsiniz.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Sertifika bağlayıcısını indirmek, yüklemek ve yapılandırmak için
![ConnectorDownload](./media/certificates-download-connector.png)   
 
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.
4. **Cihaz yapılandırması** bölmesinde **Sertifika Yetkilisi**’ni seçin.
5. **Ekle**'ye tıklayın ve **Bağlayıcı dosyasını indir**'i seçin. İndirilen dosyayı, onu yükleyeceğiniz sunucuda erişebileceğiniz bir konuma kaydedin. 
6.  İndirme tamamlandıktan sonra Basit Sertifika Kayıt Protokolü (NDES) rolünü barındıran sunucuda indirilen yükleyiciyi (**ndesconnectorssetup.exe**) çalıştırın. Yükleyici, NDES ve CRP Web Hizmeti için ilke modülünü de yükler. (CRP Web Hizmeti, CertificateRegistrationSvc, IIS'de bir uygulama olarak çalışır.)

    > [!NOTE]
    > Tek başına Intune için NDES yüklediğinizde, CRP hizmeti Sertifika Bağlayıcısı ile otomatik olarak yüklenir. Intune’u Configuration Manager ile kullandığınızda, Sertifika Kayıt Noktası'nı ayrı bir site sistem rolü olarak yüklersiniz.

3.  Sertifika Bağlayıcısı için istemci sertifikası istendiğinde, **Seç** düğmesini seçin ve ardından Görev 3'te NDES Sunucunuza yüklediğiniz **istemci kimlik doğrulaması** sertifikasını seçin.

    İstemci kimlik doğrulaması sertifikasını seçtikten sonra, **Microsoft Intune Sertifika Bağlayıcısı için İstemci Sertifikası** yüzeyine dönersiniz. Seçtiğiniz sertifika gösterilmese de bu sertifikanın özelliklerini görüntülemek **İleri** 'ye tıklayın. Ardından **İleri**'ye ve **Yükle**'ye tıklayın.

4.  Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

    > [!TIP]
    > Sertifika Bağlayıcısı Kullanıcı Arabirimi'ni başlatmadan sihirbazı kapatırsanız, aşağıdaki komutu çalıştırarak yeniden açabilirsiniz:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **Sertifika Bağlayıcısı** kullanıcı arabiriminde:

    **Oturum Aç**'a tıklayın ve Intune hizmet yöneticisi kimlik bilgilerinizi veya genel yönetim izni olan bir kiracı yöneticiye ait kimlik bilgilerini girin.

    > [!IMPORTANT]
    > Kullanıcı hesabına geçerli bir Intune lisansı atanmış olması gerekir. Kullanıcı hesabının geçerli bir Intune lisansı yoksa, NDESConnectorUI.exe başarısız olur.

    Kuruluşunuz bir ara sunucu kullanıyorsa ve NDES sunucusunun İnternet'e erişmesi için ara sunucu gerekliyse, **Ara sunucuyu kullan**'a tıklayın ve bağlanmak için ara sunucu adını, bağlantı noktasını ve hesap kimlik bilgilerini girin.

    **Gelişmiş** sekmesini seçin ve ardından, Sertifika Verme Yetkilisi'nde **Sertifika Ver ve Yönet** iznine sahip olan bir hesabın kimlik bilgilerini sağlayın ve **Uygula**'ya tıklayın.

    Şimdi Sertifika Bağlayıcısı kullanıcı arabirimini kapatabilirsiniz.

6.  Bir komut istemi açıp **services.msc** yazın ve **Enter** tuşuna basın, sonra **Intune Bağlayıcı Hizmeti**'ne sağ tıklayın ve **Yeniden Başlat**'a tıklayın.

Hizmetin çalıştığını doğrulamak için bir tarayıcı açın ve bir **403** hatası döndürmesi gereken aşağıdaki URL'yi girin:

**http:// &lt;NDES_sunucunuzun_FQDN_değeri&gt;/certsrv/mscep/mscep.dll**

## <a name="how-to-create-a-scep-certificate-profile"></a>Bir SCEP sertifika profili oluşturma

1. Azure portalında **Cihaz yapılandırması** iş yükünü seçin.
2. **Cihaz yapılandırması** bölmesinde **Yönet** > **Profiller**’i seçin.
3. Profiller bölmesinde **Profil oluştur**’u seçin.
4. **Profil oluştur** bölmesinde, SCEP sertifika profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinde, bu SCEP sertifikası için cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinde **SCEP sertifikası**’nı seçin.
7. **SCEP Sertifikası** bölmesinde aşağıdaki ayarları yapılandırın:
    - **Sertifika geçerlilik süresi** - Veren sertifika yetkilisinde, özel bir geçerlilik süresine izin veren **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** komutunu çalıştırdıysanız, sertifikanın süresi dolmadan önce kalan zamanı belirtebilirsiniz.<br>Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, yayımlayan sertifika yetkilisinin sertifikası için kalan geçerlilik süresinden de düşük olması gerekir. 
    - **Anahtar depolama sağlayıcısı (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) - Sertifika anahtarının depolandığı yeri belirtin. Aşağıdaki değerlerden birini seçin:
        - **Varsa Güvenilir Platform Modülü (TPM) KSP'sine, aksi halde Yazılım KSP'sine kaydol**
        - **Güvenilir Platform Modülü (TPM) KSP'sine kaydol, aksi halde hata ver**
        - **Passport'a kaydet, aksi halde hata ver (Windows 10 ve üzeri)**
        - **Software KSP’ye kaydol**
    - **Konu adı biçimi** - Listeden, sertifika isteğindeki konu adının Intune tarafından otomatik olarak nasıl oluşturulacağını seçin. Sertifika bir kullanıcı içinse, konu adına kullanıcının e-posta adresini de ekleyebilirsiniz. Aşağıdakilerden birini seçin:
        - **Yapılandırılmadı**
        - **Ortak ad**
        - **E-postayı içeren ortak ad**
        - **E-posta olarak ortak ad**
        - **IMEI (Uluslararası Mobil Donanım Kimliği)**
        - **Seri numarası**
        - **Özel** - Bu seçeneği belirlediğinizde, başka bir açılan alan görüntülenir. Bu alanı özel bir konu adı biçimi girmek için kullanın. Özel biçim için desteklenen iki değişken **Ortak Ad (CN)** ve **E-posta (E)** değişkenleridir. Bu değişkenlerin birinin veya ikisinin ve statik dizelerin bir bileşimini kullanarak şunun gibi özel bir konu adı biçimi oluşturabilirsiniz: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finans Grubu,L=Redmond,ST=Washington,C=ABD** Bu örnekte, CN ve E değişkenlerine ek olarak Kuruluş Birimi, Kuruluş, Konum, Eyalet ve Ülke değerleri için de dizeler kullanan bir konu adı biçimi oluşturulmuştur. [Bu konu](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx), **CertStrToName** işlevini ve bu işlevin desteklenen dizelerini gösterir.
        
    - **Konu diğer adı** - Intune uygulamasının, sertifika isteğinde konu diğer adı (SAN) için değerleri otomatik olarak nasıl oluşturacağını belirtin. Örneğin, bir kullanıcı sertifikası türü seçtiyseniz, konu alternatif adına kullanıcı asıl adını (UPN) ekleyebilirsiniz. İstemci sertifikası, bir Ağ İlkesi Sunucusuna kimlik doğrulamak için kullanılıyorsa, UPN'ye konu alternatif adını ayarlamanız gerekir. 
    - **Anahtar kullanımı** - Sertifika için anahtar kullanımı seçeneklerini belirtin. Aşağıdaki seçeneklerden birini seçebilirsiniz: 
        - **Anahtar şifreleme:** Yalnızca anahtar şifreli olduğunda anahtar değişimine izin verin. 
        - **Dijital imza:** Yalnızca anahtarın korunmasına bir dijital imza yardımcı olduğunda anahtar değişimine izin verin. 
    - **Anahtar boyutu (bit)** - Anahtarın içerdiği bit sayısını seçin. 
    - **Karma algoritması** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) - Bu sertifika ile kullanmak için uygun karma algoritması türlerinden birini seçin. Bağlanan cihazların destekleyeceği en güçlü güvenlik düzeyini seçin. 
    - **Kök Sertifika** - Daha önce yapılandırdığınız ve kullanıcıya veya cihaza atadığınız kök CA sertifika profilini seçin. Bu CA sertifikası, bu sertifika profilinde yapılandırdığınız sertifikayı veren CA'nın kök sertifikası olmalıdır. 
    - **Genişletilmiş anahtar kullanımı** - Sertifikanın hedeflenen amacına yönelik değerleri eklemek için **Ekle**'yi seçin. Çoğu durumda, kullanıcı veya cihazın bir sunucuya kimliğini doğrulayabilmesi için, sertifika **İstemci Kimlik Doğrulaması** gerektirir. Ancak, gerektiğinde başka herhangi bir anahtar kullanımı ekleyebilirsiniz. 
    - **Kayıt Ayarları**
        - **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
        - **SCEP Sunucu URL’leri** - SCEP aracılığıyla sertifika veren NDES Sunucuları için bir veya birden çok URL belirtin. 
8. **Tamam**'ı seçin, **Profil oluştur** bölmesine dönün ve **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi bölmesinde görüntülenir.

## <a name="how-to-assign-the-certificate-profile"></a>Sertifika profilini atama

Gruplara sertifika profillerini atamadan önce aşağıdaki noktaları göz önünde bulundurun:

- Sertifika profillerini gruplara atadığınızda, Güvenilen CA sertifika profilinden alınan sertifika dosyası cihaza yüklenir. Cihaz, bir sertifika isteği oluşturmak için SCEP sertifika profilini kullanır.
- Sertifika profilleri, yalnızca profili oluşturduğunuzda kullandığınız platformu çalıştıran cihazlara yüklenir.
- Sertifika profillerini kullanıcı koleksiyonlarına veya cihaz koleksiyonlarına atayabilirsiniz.
- Cihaz kaydolduktan sonra cihaza hızlıca bir sertifika yayımlamak için sertifika profilini bir cihaz grubu yerine bir kullanıcı grubuna atayın. Bir cihaz grubuna atarsanız, ilkeleri almadan önce cihazın tam olarak kaydedilmesi gerekir.
- Her profili ayrı olarak atasanız da Güvenilen Kök CA’sını ve SCEP veya PKCS profilini de atamanız gerekir. Aksi takdirde SCEP veya PKCS sertifika ilkesi başarısız olur.

Profillerin nasıl atanacağı hakkında bilgi için bkz. [Cihaz profillerini atama](device-profile-assign.md).

