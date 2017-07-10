---
title: "Intune ile PKCS sertifikalarını yapılandırma ve yönetme"
titleSuffix: Intune on Azure
description: "Altyapınızı yapılandırıp, ardından Intune ile PKCS sertifika profilleri oluşturup atamayı öğrenin.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 305a4d79aa81bd599369e72bc0cb307fdf452643
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve yönetme
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu başlığında altyapınızı yapılandırıp, ardından Intune ile PKCS sertifika profilleri oluşturup atama işlemlerinin nasıl yapılacağı gösterilir.

Kuruluşunuzda sertifika tabanlı kimlik doğrulamaları yapmak için, bir Kuruluş Sertifika Yetkiliniz olmalıdır.

Kuruluş Sertifika Yetkilisine ek olarak PKCS Sertifika profillerini de kullanmak için, aşağıdakiler gerekir:

-   Sertifika Yetkilisi ile iletişim kurabilen bir bilgisayarı veya Sertifika Yetkilisi bilgisayarını kullanabilirsiniz.

-  Sertifika Yetkilisi ile iletişim kurabilen bilgisayarda çalışan Intune Sertifika Bağlayıcısı.

## <a name="important-terms"></a>Önemli koşullar


-    **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucular (Web Uygulaması Ara Sunucusu hariç), Active Directory etki alanınıza katılmalıdır.

-  **Sertifika Yetkilisi**: Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. Bir Sertifika Yetkilisi'ni nasıl ayarlayacağınız hakkında bilgi edinmek için bkz. [Sertifika Yetkilisi'ni Yükleme](http://technet.microsoft.com/library/jj125375.aspx).
    CA'nız Windows Server 2008 R2 çalıştırıyorsa, [KB2483564 ile gelen düzeltmeyi yüklemeniz](http://support.microsoft.com/kb/2483564/)gerekir.

-  **Sertifika Yetkilisiyle iletişim kurabilen bilgisayar**: Alternatif olarak, Sertifika Yetkisi bilgisayarının kendisini kullanın.
-  **Microsoft Intune Sertifika Bağlayıcısı**: Azure Portal’dan **Sertifika Bağlayıcısı** yükleyicisini (**ndesconnectorssetup.exe**) indirirsiniz. Ardından, Sertifika Bağlayıcısı'nı yüklemek istediğiniz bilgisayarda **ndesconnectorssetup.exe** dosyasını çalıştırabilirsiniz. PKCS Sertifika profilleri için, Sertifika Bağlayıcısı’nı Sertifika Yetkilisi ile iletişim kurabilen bilgisayara yükleyin.
-  **Web Uygulaması Proxy sunucusu** (isteğe bağlı): Web Uygulaması Proxy (WAP) sunucusu olarak Windows Server 2012 R2 veya üzerini çalıştıran bir sunucu kullanabilirsiniz. Bu yapılandırma:
    -  Cihazların bir İnternet bağlantısını kullanarak sertifikaları almasını sağlar.
    -  Cihazlar sertifikaları almak ve yenilemek için İnternet üzerinden bağlanıyorsa güvenlik açısından önerilir.

 > [!NOTE]           
> -    WAP'ı barındıran sunucu, Ağ Cihazı Kayıt Hizmeti (NDES) tarafından kullanılan uzun URL'ler için destek sağlayan [bir güncelleştirmeyi yüklemelidir](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx). Bu güncelleştirmeyi [Aralık 2014 güncelleştirme paketi](http://support.microsoft.com/kb/3013769)ile birlikte veya [KB3011135](http://support.microsoft.com/kb/3011135)güncelleştirmesinden tek başına edinebilirsiniz.
>-  Ayrıca, WAP’yi barındıran sunucuda, dış istemcilere yayımlanan adla eşleşen bir SSL sertifikası olmalı ve NDES sunucusunda kullanılan SSL sertifikasına güvenilmelidir. Bu sertifikalar, WAP sunucusunun istemcilerden gelen SSL bağlantıyı sonlandırmasına ve NDES sunucusuna yeni bir SSL bağlantı oluşturmasına imkan sağlar.
    WAP sertifikaları hakkında bilgi için, [Web Uygulaması Ara Sunucusu Kullanarak Uygulama Yayınlamayı Planlama](https://technet.microsoft.com/library/dn383650.aspx) konusunun **Sertifikaları planlama** bölümüne bakın. WAP sunucuları hakkında genel bilgi için bkz. [Web Uygulaması Ara Sunucusu ile çalışma](http://technet.microsoft.com/library/dn584113.aspx).|


## <a name="certificates-and-templates"></a>Sertifikalar ve şablonlar

|Nesne|Ayrıntılar|
|----------|-----------|
|**Sertifika Şablonu**|Bu şablonu sertifika veren CA'nız üzerinde yapılandırabilirsiniz.|
|**Güvenilen Kök CA sertifika**|Bunu sertifika veren CA'dan veya ona güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarabilir ve Güvenilen CA sertifika profilini kullanarak cihazlara atayabilirsiniz.<br /><br />İşletim sistemi platformu başına tek bir Güvenilen Kök CA sertifika kullanırsınız ve bu sertifikayı oluşturduğunuz her Güvenilen Kök Sertifika profili ile ilişkilendirirsiniz.<br /><br />Gerektiğinde ek Güvenilen Kök CA sertifikaları kullanabilirsiniz. Örneğin, Wi-Fi erişim noktalarınız için sunucu kimlik doğrulama sertifikalarını imzalayan bir CA'ya güven sağlamak için bunu yapabilirsiniz.|


## <a name="configure-your-infrastructure"></a>Altyapınızı yapılandırın
Sertifika profillerini yapılandırabilmeniz için önce aşağıdaki adımları tamamlamanız gerekir. Bu adımlar, Windows Server 2012 R2 ve Active Directory Sertifika Hizmetleri (ADCS) bilgisi gerektirir:

- **Adım 1** - Sertifika yetkilisinde sertifika şablonlarını yapılandırın.
- **Adım 2** - Intune Sertifika Bağlayıcısı'nı etkinleştirin, yükleyin ve yapılandırın.

## <a name="step-1---configure-certificate-templates-on-the-certification-authority"></a>Adım 1 - Sertifika yetkilisinde sertifika şablonlarını yapılandırma

### <a name="to-configure-the-certification-authority"></a>Sertifika yetkilisini yapılandırmak için

1.  Sertifika veren CA'da, Sertifika Şablonları ek bileşenini kullanarak PKCS ile kullanılmak üzere yeni bir özel şablon oluşturun veya var olan bir şablonu (Kullanıcı şablonu gibi) kopyalayın ve düzenleyin.

    Şablon şunları içermelidir:

    -   Şablon için kolay bir **Şablon görünen adı** belirtin.

    -   **Konu Adı** sekmesinde, **İstekte sağla**'yı seçin. (Güvenlik, NDES için Intune ilke modülü tarafından zorunlu tutulur).

    -   **Uzantılar** sekmesinde, **Uygulama İlkeleri Açıklaması** 'nın **İstemci Kimlik Doğrulaması**'nı içerdiğinden emin olun.

        > [!IMPORTANT]
        > iOS ve macOS sertifika şablonları için, **Uzantılar** sekmesinde **Anahtar Kullanımı**'nı düzenleyin ve **İmza kaynağın delilidir** öğesinin seçili olmadığından emin olun.

2.  Şablonun **Genel** sekmesindeki **Geçerlilik süresi** 'ni gözden geçirin. Varsayılan olarak, Intune şablonda yapılandırılan değeri kullanır. Ancak, CA'yı istekte bulunan kişinin farklı bir değer belirtmesine izin verecek şekilde yapılandırma seçeneğiniz vardır ve bu değeri Intune yönetim konsolundan ayarlayabilirsiniz. Her zaman şablondaki değeri kullanmak istiyorsanız, bu adımın geri kalanını atlayın.

    > [!IMPORTANT]
    > iOS ve macOS, yaptığınız diğer yapılandırmalar ne olursa olsun, her zaman şablonda ayarlanan değeri kullanır.

    CA'yı istekte bulunan kişinin geçerlilik süresini belirlemesine izin verecek şekilde yapılandırmak için CA'da aşağıdaki komutları çalıştırın:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Sertifika veren CA'da, sertifika şablonunu yayımlamak için Sertifika Yetkilisi ek bileşenini kullanın.

    a.  **Sertifika Şablonları** düğümünü seçin, **Eylem**-&gt; **Yeni** &gt; **Verilecek Sertifika Şablonu** öğesine tıklayın ve ardından 2. adımda oluşturduğunuz şablonu seçin.

    b.  Şablonu **Sertifika Şablonları** klasöründe görüntüleyerek yayımlandığını doğrulayın.

4.  CA bilgisayarında, Intune Sertifika Bağlayıcısı’nı barındıran bilgisayarın, PKCS sertifika profili oluşturulurken kullanılan şablona erişebilmesi için kayıt izni olduğundan emin olun. CA bilgisayarı özelliklerindeki **Güvenlik** sekmesinde bu izni ayarlayın.

## <a name="step-2---enable-install-and-configure-the-intune-certificate-connector"></a>Adım 2 - Intune sertifika bağlayıcısını etkinleştirme, yükleme ve yapılandırma
Bu adımda şunları yapacaksınız:

- Sertifika Bağlayıcısı desteğini etkinleştirme
- Sertifika Bağlayıcısı'nı indirme, yükleme ve yapılandırma.

### <a name="to-enable-support-for-the-certificate-connector"></a>Sertifika bağlayıcısı desteğini etkinleştirmek için

1.  Azure Portal’da oturum açın.
2.  **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3.  **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
2.  **Cihaz Yapılandırması** dikey penceresinde **Kurulum** > **Sertifika Yetkilisi**’ni seçin.
2.  **1. Adım**’ın altında **Etkinleştir**’i seçin.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>Sertifika bağlayıcısını indirmek, yüklemek ve yapılandırmak için

1.  **Cihazları yapılandır** dikey penceresinde **Kurulum** > **Sertifika Yetkilisi**’ni seçin.
2.  **Sertifika bağlayıcısını indir**’i seçin.
2.  Yükleme tamamlandıktan sonra, indirilen yükleyiciyi (**ndesconnectorssetup.exe**) çalıştırın.
  Yükleyiciyi, Sertifika Yetkilisi ile iletişim kurabilen bilgisayarda çalıştırın. PKCS (PFX) Dağıtımı seçeneğini belirtin, sonra **Yükle**’yi seçin. Yükleme tamamlandığında, [Sertifika profillerini yapılandırma](certificates-configure.md) konusunda açıklandığı gibi bir sertifika profili oluşturarak devam edin.

3.  Sertifika Bağlayıcısı için istemci sertifikası istendiğinde, **Seç** düğmesini seçin ve yüklediğiniz **istemci kimlik doğrulaması** sertifikasını seçin.

    İstemci kimlik doğrulaması sertifikasını seçtikten sonra, **Microsoft Intune Sertifika Bağlayıcısı için İstemci Sertifikası** yüzeyine dönersiniz. Seçtiğiniz sertifika gösterilmese de bu sertifikanın özelliklerini görüntülemek **İleri**'yi seçin. Sonra **İleri**’yi ve ardından **Yükle**’yi seçin.

4.  Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

    > [!TIP]
    > Sertifika Bağlayıcısı Kullanıcı Arabirimi'ni başlatmadan sihirbazı kapatırsanız, aşağıdaki komutu çalıştırarak yeniden açabilirsiniz:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **Sertifika Bağlayıcısı** kullanıcı arabiriminde:

    a. **Oturum Aç**'ı seçin ve Intune hizmet yöneticisi kimlik bilgilerinizi veya genel yönetim izni olan bir kiracı yöneticiye ait kimlik bilgilerini girin.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    b. **Gelişmiş** sekmesini seçin ve ardından Sertifika Yetkiliniz’de **Sertifikaları Yayımla ve Yönet** iznine sahip olan bir hesabın kimlik bilgilerini sağlayın.

    c. **Uygula**'yı seçin.

    Şimdi Sertifika Bağlayıcısı kullanıcı arabirimini kapatabilirsiniz.

6.  Bir komut istemi açın ve **services.msc** yazın. **Enter** tuşuna basın, **Intune Bağlayıcısı Hizmeti**’ne sağ tıklayın ve **Yeniden Başlat**’ı seçin.

Hizmetin çalıştığını doğrulamak için bir tarayıcı açın ve bir **403** hatası döndürmesi gereken aşağıdaki URL'yi girin:

**http:// &lt;NDES_sunucunuzun_FQDN_değeri&gt;/certsrv/mscep/mscep.dll**


### <a name="how-to-create-a-pkcs-certificate-profile"></a>PKCS sertifika profili oluşturma

Azure Portal’da **Cihazları yapılandır** iş yükünü seçin.
2. **Cihaz yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’a tıklayın.
4. **Profil Oluştur** dikey penceresinde, PKCS sertifika profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinde, bu PKCS sertifikası için cihaz platformu olarak aşağıdakilerden birini seçin:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinde **PKCS sertifikası**’nı seçin.
7. **PKCS Sertifikası** dikey penceresinde aşağıdaki ayarları yapılandırın:
    - **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
    - **Sertifika geçerlilik süresi** - Veren sertifika yetkilisinde, özel bir geçerlilik süresine izin veren **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** komutunu çalıştırdıysanız, sertifikanın süresi dolmadan önce kalan zamanı belirtebilirsiniz.<br>Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, yayımlayan sertifika yetkilisinin sertifikası için kalan geçerlilik süresinden de düşük olması gerekir.
    - **Anahtar depolama alanı sağlayıcısı (KSP)** (Windows 10) - Sertifika anahtarının depolanacağı yeri belirtin. Aşağıdaki değerlerden birini seçin:
        - **Varsa Güvenilir Platform Modülü (TPM) KSP'sine, aksi halde Yazılım KSP'sine kaydol**
        - **Güvenilir Platform Modülü (TPM) KSP'sine kaydol, aksi halde hata ver**
        - **Passport'a kaydet, aksi halde hata ver (Windows 10 ve üzeri)**
        - **Software KSP’ye kaydol**
    - **Sertifika yetkilisi** - Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. Bir Sertifika Yetkilisi'ni nasıl ayarlayacağınız hakkında bilgi edinmek için bkz. [Sertifika Yetkilisi'ni Yükleme](http://technet.microsoft.com/library/jj125375.aspx). CA'nız Windows Server 2008 R2 çalıştırıyorsa, [KB2483564 ile gelen düzeltmeyi yüklemeniz](http://support.microsoft.com/kb/2483564/)gerekir.
    - **Sertifika yetkilisi adı** - Sertifika yetkilinizin adını girin.
    - **Sertifika şablonu adı** - Ağ Cihazı Kayıt Hizmeti'nin kullanmak üzere yapılandırıldığı ve sertifikayı veren sertifika yetkilisine eklenmiş bir sertifika şablonunun adını girin.
    Adın, Ağ Cihazı Kayıt Hizmeti'ni çalıştıran sunucunun kayıt defterinde listelenen sertifika şablonlarından biriyle tam olarak aynı olduğundan emin olun. Sertifika şablonu ekran adını değil, sertifika şablonu adını belirttiğinizden emin olun. 
    Sertifika şablonlarının adlarını bulmak için şu anahtara gidin: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. **EncryptionTemplate**, **GeneralPurposeTemplate**ve **SignatureTemplate**için değerler olarak listelenen sertifika şablonlarını göreceksiniz. Varsayılan olarak, sertifika şablonlarının üçü için de değer IPSECIntermediateOffline'dır; bu, **IPSec (Çevrimdışı istek)** şablon ekran adına eşlenir. 
    - **Konu adı biçimi** - Listeden, sertifika isteğindeki konu adının Intune tarafından otomatik olarak nasıl oluşturulacağını seçin. Sertifika bir kullanıcı içinse, konu adına kullanıcının e-posta adresini de ekleyebilirsiniz. Aşağıdakilerden birini seçin:
        - **Yapılandırılmadı**
        - **Ortak ad**
        - **E-postayı içeren ortak ad**
        - **E-posta olarak ortak ad**
    - **Konu diğer adı** - Intune uygulamasının, sertifika isteğinde konu diğer adı (SAN) için değerleri otomatik olarak nasıl oluşturacağını belirtin. Örneğin, bir kullanıcı sertifikası türü seçtiyseniz, konu alternatif adına kullanıcı asıl adını (UPN) ekleyebilirsiniz. İstemci sertifikası bir Ağ İlkesi Sunucusunda kimlik doğrulamak için kullanılacaksa, konu alternatif adını UPN olarak ayarlayın. 
    **Özel Azure AD özniteliği**'ni de seçebilirsiniz. Bu seçeneği belirlediğinizde, başka bir açılan alan görüntülenir. **Özel Azure AD özniteliği** açılan alanında bir seçenek bulunur: **Departman**. Bu seçeneği işaretlediğinizde, Azure AD'de Departman tanımlanmamışsa, sertifika verilmez. Bu sorunu çözmek için, departmanı tanımlayın ve değişiklikleri kaydedin. Bir sonraki iade etmede, sorun çözümlenir ve sertifika verilir. ASN.1 bu alan için kullanılan gösterimidir. 
    - **Genişletilmiş anahtar kullanımı** (Android) - Sertifikaların hedeflenen amacına yönelik değerler eklemek için **Ekle**'yi seçin. Çoğu durumda, kullanıcı veya cihazın bir sunucuya kimlik doğrulaması gerçekleştirebilmesi için, sertifika **İstemci Kimlik Doğrulaması** gerektirir. Ancak, gerektiğinde başka herhangi bir anahtar kullanımı ekleyebilirsiniz. 
    - **Kök Sertifika** (Android) - Daha önce yapılandırdığınız ve kullanıcıya veya cihaza atadığınız kök CA sertifika profilini seçin. Bu CA sertifikası, bu sertifika profilinde yapılandırdığınız sertifikayı verecek CA'nın kök sertifikası olmalıdır. Bu, daha önce oluşturduğunuz güvenilen sertifika profilidir.
8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**'a tıklayın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="how-to-assign-the-certificate-profile"></a>Sertifika profilini atama

Gruplara sertifika profillerini atamadan önce aşağıdaki noktaları göz önünde bulundurun:

- Sertifika profillerini gruplara atadığınızda, Güvenilen CA sertifika profilinden alınan sertifika dosyası cihaza yüklenir. Cihaz, bir sertifika isteği oluşturmak için PKCS sertifika profilini kullanır.
- Sertifika profilleri, yalnızca profili oluşturduğunuzda kullandığınız platformu çalıştıran cihazlara yüklenir.
- Sertifika profillerini kullanıcı koleksiyonlarına veya cihaz koleksiyonlarına atayabilirsiniz.
- Cihaz kaydolduktan sonra cihaza hızlıca bir sertifika yayımlamak için sertifika profilini bir cihaz grubu yerine bir kullanıcı grubuna atayın. Bir cihaz grubuna atarsanız, ilkeleri almadan önce cihazın tam olarak kaydedilmesi gerekir.
- Her profili ayrı olarak atasanız da Güvenilen Kök CA’sını ve PKCS profilini de atamanız gerekir. Aksi takdirde PKCS sertifika ilkesi başarısız olur.

Profillerin nasıl atanacağı hakkında bilgi için bkz. [Cihaz profillerini atama](device-profile-assign.md).
