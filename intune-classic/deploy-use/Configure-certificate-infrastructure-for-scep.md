---
title: "SCEP için sertifika altyapısını yapılandırma |Microsoft Docs"
description: "SCEP sertifika profillerini oluşturmaya veya dağıtmaya yönelik altyapı."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ae137ae-34e5-4a45-950c-983de831270f
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 88fd05cf1ccaf2c033b737ce76a3ce5d83557313
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---
# <a name="configure-certificate-infrastructure-for-scep"></a>SCEP için sertifika altyapısını yapılandırma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu başlığı altında, SCEP sertifika profillerini oluşturmak ve dağıtmak için hangi altyapıya ihtiyacınız olduğu açıklanır.

### <a name="on-premises-infrastructure"></a>Şirket içi altyapı

-    **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucular (Web Uygulaması Ara Sunucusu hariç), Active Directory etki alanınıza katılmalıdır.

-  **Sertifika Yetkilisi** (CA): Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. Bir Sertifika Yetkilisi'ni nasıl ayarlayacağınız hakkında bilgi edinmek için bkz. [Sertifika Yetkilisi'ni Yükleme](http://technet.microsoft.com/library/jj125375.aspx).
    CA'nız Windows Server 2008 R2 çalıştırıyorsa, [KB2483564 ile gelen düzeltmeyi yüklemeniz](http://support.microsoft.com/kb/2483564/)gerekir.
I
-  **NDES Sunucusu**: Windows Server 2012 R2 veya üstünü çalıştıran bir sunucuya Ağ Cihazı Kayıt Hizmeti’ni (NDES) kurmalısınız. Intune, Kuruluş CA ile aynı sunucuda çalıştırılan NDES’nin kullanımını desteklemez. Windows Server 2012 R2’yi Ağ Cihazı Kayıt Hizmeti’ni barındıracak şekilde yapılandırma yönergeleri için bkz. [Ağ Cihazı Kayıt Hizmeti Kılavuzu](http://technet.microsoft.com/library/hh831498.aspx). NDES sunucusu CA’yı barındıran etki alanına katılmış olmalı ve CA ile aynı sunucuda yer almamalıdır. NDES sunucusunu ayrı bir ormanda, yalıtılmış ağda veya iç etki alanında dağıtma hakkında daha fazla bilgi, [Ağ Cihazı Kayıt Hizmeti ile İlke Modülü Kullanma](https://technet.microsoft.com/library/dn473016.aspx) başlığı altında bulunabilir.

-  **Microsoft Intune Sertifika Bağlayıcısı**: **Sertifika Bağlayıcısı** yükleyicisini (**ndesconnectorssetup.exe**) indirmek için Intune yönetim konsolunu kullanırsınız. Ardından, Sertifika Bağlayıcısı'nı yüklemek istediğiniz bilgisayarda **ndesconnectorssetup.exe** dosyasını çalıştırabilirsiniz.
-  **Web Uygulaması Ara Sunucusu** (isteğe bağlı): Web Uygulaması Ara Sunucusu (WAP) olarak Windows Server 2012 R2 veya üstünü çalıştıran bir sunucu kullanabilirsiniz. Bu yapılandırma:
    -  Cihazların bir İnternet bağlantısını kullanarak sertifikaları almasını sağlar.
    -  Cihazlar sertifikaları almak ve yenilemek için İnternet üzerinden bağlanıyorsa güvenlik açısından önerilir.

 > [!NOTE]           
> -    WAP'ı barındıran sunucular, Ağ Cihazı Kayıt Hizmeti tarafından kullanılan uzun URL'ler için destek sağlayan [bir güncelleştirmeyi yüklemelidir](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) . Bu güncelleştirmeyi [Aralık 2014 güncelleştirme paketi](https://support.microsoft.com/kb/3013769)ile birlikte veya [KB3011135](https://support.microsoft.com/kb/3011135)güncelleştirmesinden tek başına edinebilirsiniz.
>-  Ayrıca, WAP’yi barındıran sunucuda, dış istemcilere yayımlanan adla eşleşen bir SSL sertifikası olmalı ve NDES sunucusunda kullanılan SSL sertifikasına güvenilmelidir. Bu sertifikalar, WAP sunucusunun istemcilerden gelen SSL bağlantıyı sonlandırmasına ve NDES sunucusuna yeni bir SSL bağlantı oluşturmasına imkan sağlar.
    WAP sertifikaları hakkında bilgi için, [Web Uygulaması Ara Sunucusu Kullanarak Uygulama Yayınlamayı Planlama](https://technet.microsoft.com/library/dn383650.aspx) konusunun **Sertifikaları planlama** bölümüne bakın. WAP sunucuları hakkında genel bilgi için bkz. [Web Uygulaması Ara Sunucusu ile çalışma](http://technet.microsoft.com/library/dn584113.aspx).|

### <a name="network-requirements"></a>Ağ gereksinimleri

İnternet’ten çevre ağına, İnternet’te tüm konaklardan/IP adreslerinden NDES sunucusuna bağlantı noktası 443’e izin verin.

Çevre ağından güvenilen ağa, etki alanına katılmış NDES sunucusunda etki alanı erişimi için gereken tüm bağlantı noktalarına ve protokollere izin verin. NDES sunucusunun sertifika sunucularına, DNS sunucularına, Configuration Manager sunucularına ve etki alanı denetleyicilerine erişimi olmalıdır.

NDES sunucusunun [Azure AD uygulama proxy’si](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Erişim Proxy](https://technet.microsoft.com/library/dn584107.aspx)’si veya üçüncü taraf bir proxy gibi bir proxy aracılığıyla yayımlanmasını öneririz.


### <a name="BKMK_CertsAndTemplates"></a>Sertifikalar ve Şablonlar

|Nesne|Ayrıntılar|
|----------|-----------|
|**Sertifika Şablonu**|Bu şablonu sertifika veren CA'nız üzerinde yapılandırabilirsiniz.|
|**İstemci kimlik doğrulama sertifikası**|Sertifika veren CA'nızdan veya genel CA'dan istenen bu sertifikayı NDES Sunucusu'na yüklersiniz.|
|**Sunucu kimlik doğrulama sertifikası**|Sertifika veren CA'nızdan veya genel CA'dan istenen bu SSL sertifikasını NDES Sunucusu'ndaki IIS'de yüklersiniz ve bağlarsınız.|
|**Güvenilen Kök CA sertifika**|Bunu kök CA'dan veya kök CA’ya güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarabilir ve Güvenilen CA sertifika profilini kullanarak cihazlara dağıtabilirsiniz.<br /><br />İşletim sistemi platformu başına tek bir Güvenilen Kök CA sertifika kullanırsınız ve bu sertifikayı oluşturduğunuz her Güvenilen Kök Sertifika profili ile ilişkilendirirsiniz.<br /><br />Gerektiğinde ek Güvenilen Kök CA sertifikaları kullanabilirsiniz. Örneğin, Wi-Fi erişim noktalarınız için sunucu kimlik doğrulama sertifikalarını imzalayan bir CA'ya güven sağlamak için bunu yapabilirsiniz.|

### <a name="BKMK_Accounts"></a>Hesaplar

|Ad|Ayrıntılar|
|--------|-----------|
|**NDES hizmet hesabı**|NDES Hizmet Hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı belirtirsiniz.|

## <a name="BKMK_ConfigureInfrastructure"></a>Altyapınızı yapılandırın
Sertifika profillerini yapılandırmadan önce Windows Server 2012 R2 ve Active Directory Sertifika Hizmetleri (ADCS) bilgisi gerektiren aşağıdaki görevleri tamamlamanız gerekir:

**Görev 1**: NDES hizmet hesabı oluşturma

**Görev 2**: Sertifika yetkilisinde sertifika şablonlarını yapılandırma

**Görev 3**: NDES sunucusunda önkoşulları yapılandırma

**Görev 4**: NDES’yi Intune’la kullanılacak şekilde yapılandırma

**Görev 5**: Intune Sertifika Bağlayıcısı'nı etkinleştirme, yükleme ve yapılandırma

### <a name="task-1---create-an-ndes-service-account"></a>Görev 1 - NDES hizmet hesabı oluşturma

NDES hizmet hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı oluşturun. NDES'i yükleyip yapılandırmadan önce sertifika veren CA üstünde şablonları yapılandırırken bu hesabı belirteceksiniz. Kullanıcının varsayılan haklara (**Yerel Olarak Oturum Açma**, **Hizmet Olarak Oturum Açma** ve **Toplu İş Olarak Oturum Açma** hakları) sahip olduğundan emin olun. Bazı kuruluşların söz konusu hakları devre dışı bırakan sağlamlaştırma ilkeleri vardır.




### <a name="task-2---configure-certificate-templates-on-the-certification-authority"></a>Görev 2 - Sertifika yetkilisinde sertifika şablonlarını yapılandırma
Bu görevde şunları yapacaksınız:

-   NDES için bir sertifika şablonu yapılandırma

-   NDES için oluşturulan sertifika şablonunu yayımlama

##### <a name="to-configure-the-certification-authority"></a>Sertifika yetkilisini yapılandırmak için

1.  Kuruluş yöneticisi olarak oturum açın.

2.  Sertifika veren CA'da, Sertifika Şablonları ek bileşenini kullanarak yeni bir özel şablon oluşturun veya var olan bir şablonunu kopyalayın ve ardından, var olan bir şablonu (Kullanıcı şablonu gibi) NDES ile kullanılmak üzere düzenleyin.

    Şablonun aşağıdaki yapılandırmalara sahip olması gerekir:

    -   Şablon için kolay bir **Şablon görünen adı** belirtin.

    -   **Konu Adı** sekmesinde, **İstekte sağla**'yı seçin. (Güvenlik, NDES için Intune ilke modülü tarafından zorunlu tutulur).

    -   **Uzantılar** sekmesinde, **Uygulama İlkeleri Açıklaması** 'nın **İstemci Kimlik Doğrulaması**'nı içerdiğinden emin olun.

        > [!IMPORTANT]
        > iOS ve Mac OS X sertifika şablonları için, **Uzantılar** sekmesinde **Anahtar Kullanımı**'nı düzenleyin ve **İmza kaynağın delilidir** öğesinin seçili olmadığından emin olun.

    -   **Güvenlik** sekmesinde, NDES hizmet hesabını ekleyin ve bu hesaba şablon üzerinde **Kaydetme** izinleri verin. SCEP profillerini oluşturacak olan Intune yöneticilerinin, SCEP profillerini oluştururken şablona göz atabilmeleri için **Okuma** hakları olmalıdır.

    > [!NOTE]
    > Sertifikaları iptal etmek için, NDES hizmet hesabının sertifika profili tarafından kullanılan her sertifika şablonu üzerinde *Sertifikaları Yayımlama ve Yönetme* hakları olmalıdır.

3.  Şablonun **Genel** sekmesindeki **Geçerlilik süresi** 'ni gözden geçirin. Varsayılan olarak, Intune şablonda yapılandırılan değeri kullanır. Ancak, CA'yı istekte bulunan kişinin farklı bir değer belirtmesine izin verecek şekilde yapılandırma seçeneğiniz vardır ve bu değeri Intune yönetim konsolundan ayarlayabilirsiniz. Her zaman şablondaki değeri kullanmak istiyorsanız, bu adımın geri kalanını atlayın.

    > [!IMPORTANT]
    > iOS ve Mac OS X platformları, yaptığınız diğer yapılandırmalar ne olursa olsun, her zaman şablonda ayarlanan değeri kullanır.

Burada, örnek şablon yapılandırmasının ekran görüntüleri verilmiştir.

![Şablon, istek işleme sekmesi](..\media\scep_ndes_request_handling.png)

![Şablon, konu adı sekmesi](..\media\scep_ndes_subject_name.jpg)

![Şablon, güvenlik sekmesi](..\media\scep_ndes_security.jpg)

![Şablon, uzantılar sekmesi](..\media\scep_ndes_extensions.jpg)

![Şablon, verme gereklilikleri sekmesi](..\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Uygulama İlkeleri için (4. ekran görüntüsü), yalnızca gerekli uygulama ilkelerini ekleyin. Seçimlerinizi güvenlik yöneticilerinizle onaylayın.



CA'yı istekte bulunan kişinin geçerlilik süresini belirlemesine izin verecek şekilde yapılandırmak için CA'da aşağıdaki komutları çalıştırın:

   1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   2.  **net stop certsvc**

   3.  **net start certsvc**

4.  Sertifika veren CA'da, sertifika şablonunu yayımlamak için Sertifika Yetkilisi ek bileşenini kullanın.

    1.  **Sertifika Şablonları** düğümünü seçin, **Eylem**-&gt; **Yeni** &gt; **Verilecek Sertifika Şablonu** öğesine tıklayın ve ardından 2. adımda oluşturduğunuz şablonu seçin.

    2.  Şablonu **Sertifika Şablonları** klasöründe görüntüleyerek yayımlandığını doğrulayın.


### <a name="task-3---configure-prerequisites-on-the-ndes-server"></a>Görev 3 - NDES sunucusunda önkoşulları yapılandırma
Bu görevde şunları yapacaksınız:

-   NDES'i bir Windows Server'a ekleyin ve IIS'yi NDES'i destekleyecek biçimde yapılandırın

-   NDES Hizmet hesabını IIS_IUSR grubuna ekleyin

-   NDES hizmet hesabı SPN'yi ayarlayın




   1.  NDES'i barındıracak sunucuda bir **Kuruluş Yöneticisi**olarak oturum açmanız ve sonra NDES'i yüklemek için [Rol ve Özellik Ekle Sihirbazı](https://technet.microsoft.com/library/hh831809.aspx) 'nı kullanmanız gerekir:

    1.  Sihirbaz'da, AD CS Rol Hizmetleri'ne erişmek için **Active Directory Sertifika Hizmetleri** 'ni seçin. **Ağ Cihazı Kayıt Hizmeti**'ni seçin, **Sertifika Yetkilisi**'nin işaretini kaldırın ve ardından sihirbazı tamamlayın.

        > [!TIP]
        > Sihirbazın **Kurulum ilerleme durumu** sayfasında **Kapat**'a tıklamayın. Bunun yerine, **Hedef sunucuda Active Directory Sertifika Hizmetleri'ni Yapılandır**bağlantısına tıklayın. Bu, sonraki görev için kullanacağınız **AD CS Yapılandırma** sihirbazını açar. AD CS Yapılandırması açıldıktan sonra, Rol ve Özellik Ekle sihirbazını kapatabilirsiniz.

    2.  NDES sunucuya eklendiğinde, sihirbaz tarafından IIS de yüklenir. IIS'nin aşağıdaki yapılandırmalara sahip olduğundan emin olun:

        -   **Web Sunucusu** &gt; **Güvenlik** &gt; **İstek Filtreleme**

        -   **Web Sunucusu** &gt; **Uygulama Geliştirme** &gt; **ASP.NET 3.5**. ASP.NET 3.5'in yüklendiğinde .NET Framework 3.5 yüklenir. .NET Framework 3.5'i yüklerken, hem çekirdek **.NET Framework 3.5** özelliğini hem de **HTTP Etkinleştirmesi**'ni yükleyin.

        -   **Web Sunucusu** &gt; **Uygulama Geliştirme** &gt; **ASP.NET 4.5**. ASP.NET 4.5 yüklendiğinde, .NET Framework 4.5 yüklenir. .NET Framework 4.5'i yüklerken, çekirdek **.NET Framework 4.5** özelliğini, **ASP.NET 4.5**'i ve **WCF Hizmetleri** &gt; **HTTP Etkinleştirmesi** özelliğini yükleyin.

        -   **Yönetim Araçları** &gt; **IIS 6 Yönetim Uyumluluğu** &gt; **IIS 6 Metatabanı Uyumluluğu**

        -   **Yönetim Araçları** &gt; **IIS 6 Yönetim Uyumluluğu** &gt; **IIS 6 WMI Uyumluluğu**

  2.  Sunucuda, NDES hizmet hesabını **IIS_IUSR** grubunun bir üyesi olarak ekleyin.

   3.  NDES hizmet hesabının SPN'sini ayarlamak için, yükseltilmiş bir komut istemcisinde şu komutu çalıştırın:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Örneğin, NDES Sunucunuzun adlı **Server01**, etki alanınız **Contoso.com**ve hizmet hesabını **NDESService**ise, şunu kullanın:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

### <a name="task-4---configure-ndes-for-use-with-intune"></a>Görev 4 - NDES’yi Intune’la kullanılacak şekilde yapılandırma
Bu görevde şunları yapacaksınız:

-   NDES'i sertifika veren CA ile kullanmak için yapılandırma

-   IIS'de sunucu kimlik doğrulaması (SSL) sertifikasını bağlama

-   IIS'de İstek Filtrelemeyi Yapılandırma

##### <a name="to-configure-ndes-for-use-with-intune"></a>NDES’yi Intune’la kullanılacak şekilde yapılandırmak için

1.  NDES Sunucusunda, AD CS Yapılandırma sihirbazını açın ve aşağıdaki yapılandırmaları yapın.

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

3. NDES sunucusu çok uzun URL’ler (sorgular) alacağı için, iki kayıt defteri girdisini eklemeniz gerekir:

    |Konum|Değer|Tür|Veri|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (ondalık)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (ondalık)|


4. IIS yöneticisinde, **Varsayılan Web Sitesi** -> **İstek Filtreleme** -> **Özellik Ayarını Düzenle**’yi seçin ve **En fazla URL uzunluğu** ve **En fazla sorgu dizesi** değerlerini gösterildiği gibi *65534* olarak değiştirin.

    ![IIS en fazla URL ve sorgu uzunluğu](..\media\SCEP_IIS_max_URL.png)

5.  Sunucuyu yeniden başlatın. Sunucuda **iisreset** komutunu çalıştırmak, bu değişiklikleri sonlandırmak için yeterli değildir.
6. Http://*FQDN*/certsrv/mscep/mscep.dll adresine göz atın. Buna benzeyen bir NDES sayfası görmelisiniz:

    ![Test NDES](..\media\SCEP_NDES_URL.png)

    **503 Hizmet kullanılamıyor** hatasını alırsanız olay görüntüleyicisini gözden geçirin. NDES kullanıcısı için bir hakkın eksik olması nedeniyle uygulama havuzu durdurulmuş olabilir. Bu haklar Görev 1'de açıklanmıştır.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>NDES Sunucusu'nda sertifikaları yüklemek ve bağlamak için

1.  NDES Sunucunuzda, iç CA'nızdan veya genel CA'dan bir **sunucu kimlik doğrulaması** sertifikası isteyin ve yükleyin. Ardından bu SSL sertifikasını IIS'de bağlarsınız.

    > [!TIP]
    > SSL sertifikasını IIS'de bağladıktan sonra, bir de istemci kimlik doğrulama sertifikası yüklersiniz. Bu sertifika, NDES Sunucusu tarafından güvenilen bir CA tarafından verilebilir. En iyi yöntem olmasa da, sertifika her iki Gelişmiş Anahtar Kullanımları (EKU'lar) özelliğine de sahip olduğu sürece, aynı sertifikayı hem sunucu hem de istemci kimlik doğrulaması için kullanabilirsiniz. Bu kimlik doğrulama sertifikaları hakkında bilgi için aşağıdaki adımları gözden geçirin.

    1.  Sunucu kimlik doğrulama sertifikasını edindikten sonra **IIS Yöneticisi**'ni açın, **Bağlantılar** bölmesinden **Varsayılan Web Sitesi** 'ni seçin ve ardından, **Eylemler** bölmesinden **Bağlamalar** 'a tıklayın.

    2.  **Ekle**'ye tıklayın, **Tür** 'ü **https**olarak ayarlayın ve sonra bağlantı noktasının **443**olduğundan emin olun. (Tek başına Intune için yalnızca bağlantı noktası 443 desteklenir.)

    3.  **SSL sertifikası**için sunucu kimlik doğrulama sertifikasını belirtin.

        > [!NOTE]
        > NDES sunucusu tek bir ağ adresi için hem iç hem de dış ad kullanıyorsa, sunucu kimlik doğrulama sertifikasının bir dış genel sunucu adına sahip bir **Konu Adı** ve iç sunucu adını içeren bir **Konu Diğer Adı** olmalıdır.

2.  NDES Sunucunuzda, iç CA'nızdan ya da genel bir sertifika yetkilisinden bir **istemci kimlik doğrulaması** sertifikası isteyin ve yükleyin. Bu sertifika, her iki özelliği de içeriyorsa sunucu kimlik doğrulama sertifikası ile aynı sertifika olabilir.

    İstemci kimlik doğrulama sertifikasının aşağıdaki özelliklere sahip olması gerekir:

    **Gelişmiş Anahtar Kullanımı** - Bu, **İstemci Kimlik Doğrulaması**'nı içermelidir.

    **Konu Adı** - Bu, sertifikayı yüklediğiniz sunucunun (NDES Sunucusu) DNS adına eşit olmalıdır.

##### <a name="to-configure-iis-request-filtering"></a>IIS İstek Filtreleme'yi yapılandırmak için

1.  NDES Sunucusu'nda **IIS Yöneticisi**'ni açın, **Bağlantılar** bölmesinden **Varsayılan Web Sitesi** 'ni seçin ve ardından **İstek Filtreleme**'yi açın.

2.  **Özellik Ayarlarını Düzenle**'ye tıklayın ve ardından aşağıdakileri ayarlayın:

    **sorgu dizesi (Bayt)** = **65534**

    **URL uzunluğu üst sınırı (Bayt)** = **65534**

3.  Aşağıdaki kayıt defteri anahtarını inceleyin:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Aşağıdaki değerlerin DWORD girişleri olarak ayarlandığından emin olun:

    Ad: **MaxFieldLength**, **65534**'ün ondalık bir değeri ile

    Ad: **MaxRequestBytes**, **65534**'ün ondalık bir değeri ile

4.  NDES sunucusunu yeniden başlatın. Sunucu artık Sertifika Bağlayıcısı'nı desteklemeye hazırdır.

### <a name="task-5---enable-install-and-configure-the-intune-certificate-connector"></a>Görev 5 - Intune Sertifika Bağlayıcısı'nı etkinleştirme, yükleme ve yapılandırma
Bu görevde şunları yapacaksınız:

Intune’da NDES desteğini etkinleştirme.

NDES Sunucusu'nda Sertifika Bağlayıcısı'nı indirme, yükleme ve yapılandırma.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Sertifika Bağlayıcısı desteğini etkinleştirmek için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın, **Yönetim** &gt; **Sertifika Bağlayıcısı**’na tıklayın.

2.  **Şirket İçi Sertifika Bağlayıcısını Yapılandır**'a tıklayın.

3.  **Sertifika Bağlayıcısı'nı Etkinleştir**'i seçin ve ardından **Tamam**'a tıklayın.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Sertifika Bağlayıcısı'nı indirmek, yüklemek ve yapılandırmak için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın ve ardından **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Sertifika Bağlayıcısı** &gt; **Sertifika Bağlayıcısı’nı İndir**’e tıklayın.

2.  Yükleme tamamlandıktan sonra, indirilen yükleyiciyi (**ndesconnectorssetup.exe**) bir Windows Server 2012 R2 sunucusunda çalıştırın. Yükleyici, NDES ve CRP Web Hizmeti için ilke modülünü de yükler. (CRP Web Hizmeti, CertificateRegistrationSvc, IIS'de bir uygulama olarak çalışır.)

    > [!NOTE]
    > Tek başına Intune için NDES yüklediğinizde, CRP hizmeti Sertifika Bağlayıcısı ile otomatik olarak yüklenir. Intune’u Configuration Manager ile kullandığınızda, Sertifika Kayıt Noktası'nı ayrı bir site sistem rolü olarak yüklersiniz.

3.  Sertifika Bağlayıcısı için istemci sertifikası istendiğinde, **Seç**'e tıklayıp Görev 3'te NDES Sunucunuza yüklediğiniz **istemci kimlik doğrulaması** sertifikasını seçin.

    İstemci kimlik doğrulaması sertifikasını seçtikten sonra, **Microsoft Intune Sertifika Bağlayıcısı için İstemci Sertifikası** yüzeyine dönersiniz. Seçtiğiniz sertifika gösterilmese de bu sertifikanın özelliklerini görüntülemek **İleri** 'ye tıklayın. Ardından **İleri**'ye ve **Yükle**'ye tıklayın.

4.  Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

    > [!TIP]
    > Sertifika Bağlayıcısı Kullanıcı Arabirimi'ni başlatmadan sihirbazı kapatırsanız, aşağıdaki komutu çalıştırarak yeniden açabilirsiniz:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **Sertifika Bağlayıcısı** kullanıcı arabiriminde:

    **Oturum Aç**'a tıklayın ve Intune hizmet yöneticisi kimlik bilgilerinizi veya genel yönetim izni olan bir kiracı yöneticiye ait kimlik bilgilerini girin.

    Kuruluşunuz bir ara sunucu kullanıyorsa ve NDES sunucusunun İnternet'e erişmesi için ara sunucu gerekliyse, **Ara sunucuyu kullan**'a tıklayın ve bağlanmak için ara sunucu adını, bağlantı noktasını ve hesap kimlik bilgilerini girin.

    **Gelişmiş** sekmesini seçin ve ardından, Sertifika Verme Yetkilisi'nde **Sertifika Ver ve Yönet** iznine sahip olan bir hesabın kimlik bilgilerini sağlayın ve **Uygula**'ya tıklayın.

    Şimdi Sertifika Bağlayıcısı kullanıcı arabirimini kapatabilirsiniz.

6.  Bir komut istemi açıp **services.msc** yazın ve **Enter** tuşuna basın, sonra **Intune Bağlayıcı Hizmeti**'ne sağ tıklayın ve **Yeniden Başlat**'a tıklayın.

Hizmetin çalıştığını doğrulamak için bir tarayıcı açın ve bir **403** hatası döndürmesi gereken aşağıdaki URL'yi girin:

**https:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

## <a name="next-steps"></a>Sonraki adımlar
Artık, [Sertifika profillerini yapılandırma](Configure-Intune-certificate-profiles.md) konusunda açıklandığı gibi sertifika profillerinizi yapılandırmaya hazırsınız.

