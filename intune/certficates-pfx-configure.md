---
title: Microsoft Intune - Azure özel ve ortak anahtar sertifikalarını kullanma | Microsoft Docs
description: Ekleme veya ortak anahtar şifreleme standartları (PKCS) sertifikaları Microsoft kök sertifikasını dışarı aktarma, sertifika şablonunu yapılandırmak, indirin ve yükleyin Microsoft Intune sertifika Bağlayıcısı'nı (NDES), oluşturma adımları da dahil olmak üzere Intune oluşturma bir cihaz yapılandırma profilini, Azure ve sertifika Yetkilinizde PKCS sertifika profili oluşturun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c2c649df23a84d8836a68fd0456da6ce8dda2c0
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837315"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve kullanma

Sertifika kimlik doğrulaması ve güvenli bir VPN veya WiFi ağına gibi şirket kaynaklarınıza erişim. Birçok kuruluşta bir genel ve özel anahtar çifti olarak da bilinen PKCS sertifikaları kullanan sertifikaları kullanılır. Microsoft Intune erişim ve kimlik doğrulaması, kuruluş kaynaklarına PKCS sertifikalarını kullanmak için yerleşik ayarlarını içerir. Bu ayarlar gönderildi (dağıtılan Intune'da cihaz yapılandırma profilleri kullanarak cihazlara veya).

Bu makalede, PKCS sertifikalarını kullanmak için gereksinimler listeler, PKCS sertifikasını dışarı aktarma ve sertifika için bir Intune cihaz yapılandırma profili ekleme işlemi gösterilmektedir.

## <a name="requirements"></a>Gereksinimler

PKCS sertifikalarını Intune ile kullanmak için aşağıdaki altyapıya sahip olduğunuzdan emin olun:

- **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucuları, Active Directory etki alanınıza katılmalıdır.

  AD DS'yi yükleme ve yapılandırma hakkında daha fazla bilgi için bkz. [AD DS Tasarımı ve Planlaması](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Sertifika yetkilisi** (CA): Bir kuruluş sertifika yetkilisi (CA)

  Active Directory Sertifika Hizmetleri'ni (AD CS) yükleme ve yapılandırma hakkında daha fazla bilgi için bkz. [Active Directory Sertifika Hizmetleri Adım Adım Kılavuzu](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune, AD CS'yi, Tek Başına bir CA yerine bir Kurumsal Sertifika Yetkilisi (CA) ile çalıştırmanızı gerektirir.

- **Bir istemci**: Kurumsal CA'ya bağlanmak için

- **Kök sertifika**: Kök sertifikanızın Kurumsal ca'ndan dışa aktarılmış bir kopyası

- **Microsoft Intune sertifika Bağlayıcısı**: İndirmek için Azure portalını kullanın **sertifika Bağlayıcısı** Yükleyicisi (**NDESConnectorSetup.exe**). 

  Bağlayıcı, kimlik doğrulama veya S/MIME e-posta imzalamaları için kullanılan PKCS sertifikası isteklerini işler.

  NDES Sertifika bağlayıcısı, Federal Bilgi İşleme Standardı (FIPS) modunu da destekler. FIPS gerekli değildir ancak etkinleştirildiğinde sertifika verebilir ve iptal edebilirsiniz.

- **PFX sertifika Bağlayıcısı Microsoft Intune için**: S/MIME e-posta şifreleme kullanmayı planlıyorsanız, indirmek için Azure portalını kullanın **PFX sertifika Bağlayıcısı için Intune** Yükleyicisi (**PfxCertificateConnectorBootstrapper.exe**). Bağlayıcı, belirli bir kullanıcı için e-posta şifreleme S/MIME için Intune'da içeri PFX dosyaları için istekleri işler.

- **Windows Server**: Konaklar:

  - Kimlik doğrulama ve S/MIME e-posta imzalama senaryoları için Microsoft Intune Sertifika Bağlayıcısı (NDESConnectorSetup.exe)
  - S/MIME e-posta şifreleme senaryoları için Microsoft Intune için PFX Sertifika Bağlayıcısı (PfxCertificateConnectorBootstrapper.exe).

  Her iki bağlayıcıyı da (**Microsoft Intune Sertifika Bağlayıcısı** ve **Microsoft Intune için PFX Sertifika Bağlayıcısı**) aynı sunucuda çalıştırabilirsiniz.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Kök sertifikayı Kurumsal CA'dan dışa aktarın

VPN, WiFi ve diğer kaynakları ile kimlik doğrulaması için kök veya ara CA sertifikasını her cihazda gereklidir. Aşağıdaki adımlar, Kurumsal CA'nızdan gerekli sertifikayı nasıl alacağınızı açıklar.

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. Yönetici olarak bir komut istemi açın.
3. Kök CA Sertifikasını (.cer), daha sonra erişebileceğiniz bir konuma dışarı aktarın.
4. Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

   `certutil -ca.cert certnew.cer`

   Daha fazla bilgi için bkz: [Sertifikaları yönetmek için Certutil görevleri](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

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
> Microsoft Intune Sertifika Bağlayıcısı, ayrı bir Windows sunucusunda yüklü **olmalıdır**. Sertifika veren Sertifika Yetkilisi’ne (CA) yüklenemez.

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri**, filtre **Intune** > seçin **Intune**.
2. **Cihaz Yapılandırması** > **Sertifika Yetkilisi** > **Ekle**’yi seçin.
3. Bağlayıcı dosyasını indirip kaydedin. Bağlayıcıyı, yükleyeceğiniz sunucudan erişilebilir bir konuma kaydedin.

    ![ConnectorDownload][ConnectorDownload]

4. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. NDES Sertifika bağlayıcısının gerektirdiği .NET 4.5 Framework veya sonraki bir sürümünün yüklü olduğundan emin olun. .NET 4.5 Framework, Windows Server 2012 R2 ve daha yeni sürümlere otomatik olarak eklenir.
    2. Yükleyiciyi (NDESConnectorSetup.exe) çalıştırın ve varsayılan konumu kabul edin. Bağlayıcı `\Program Files\Microsoft Intune\NDESConnectorUI` konumuna yüklenir. Yükleyici Seçenekleri’nde **PFX Dağıtımı**’nı seçin. Devam edin ve yüklemeyi tamamlayın.
    3. Varsayılan olarak, bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet’e erişmek için bir ara sunucu gerekiyorsa, yerel hizmet hesabının sunucudaki ara sunucu ayarlarına erişebildiğinizden emin olun.

5. NDES Bağlayıcısı, **Kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**’ı seçin ve yönetim izinleri olan bir hesap girin.
6. **Gelişmiş** sekmesinde **Bu bilgisayarın SİSTEM hesabını kullan (varsayılan)**’ı seçili bırakmanız önerilir.
7. **Uygula** > **Kapat**
8. Azure portalına dönün (**Intune** > **Cihaz Yapılandırması** > **Sertifika Yetkilisi**). Birkaç dakika sonra yeşil bir onay işareti gösterilir ve **bağlantı durumu** olduğu **etkin**. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.
9. Ağ ortamınızda bir web proxy varsa, çalışması bağlayıcıyı etkinleştirmek için ek yapılandırma gerekebilir. Daha fazla bilgi için [iş mevcut şirket içi proxy sunucuları](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) Azure Active Directory belgelerinde.

> [!NOTE]
> TLS 1.2 desteği, Microsoft Intune Sertifika Bağlayıcısı'na dahil edilmiştir. Bu nedenle Microsoft Intune Sertifika Bağlayıcısı'nın yüklü olduğu sunucu TLS 1.2’yi destekliyorsa TLS 1.2 kullanılır. Sunucu TLS 1.2 desteklemiyorsa TLS 1.1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>Microsoft Intune için PFX Sertifika Bağlayıcısı

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz Yapılandırması** > **Sertifika Yetkilisi** > **Ekle** seçeneğini belirleyin
3. Microsoft Intune için PFX Sertifika Bağlayıcısı’nı indirin ve kaydedin. Bağlayıcıyı, yükleyeceğiniz sunucudan erişilebilir bir konuma kaydedin.
4. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. Microsoft Intune için PFX Sertifika Bağlayıcısı'nın gerektirdiği .NET 4.6 Framework veya sonraki bir sürümünün yüklü olduğundan emin olun. .NET 4.6 Framework yüklü değilse yükleyici bunu otomatik olarak yükler.
    2. Yükleyiciyi (PfxCertificateConnectorBootstrapper.exe) çalıştırın ve varsayılan konumu kabul edin. Bağlayıcı `Program Files\Microsoft Intune\PFXCertificateConnector` konumuna yüklenir.
    3. Bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet erişimi için bir ara sunucu gerekiyorsa, yerel hizmet hesabının sunucudaki ara sunucu ayarlarına erişebildiğinizden emin olun.

5. Microsoft Intune için PFX Sertifika Bağlayıcısı yüklendikten sonra **Kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**'ı seçin ve Azure genel yöneticisi veya Intune yöneticisi izinleri olan bir hesap girin.
6. Pencereyi kapatın.
7. Azure portalına dönün (**Intune** > **Cihaz Yapılandırması** > **Sertifika Yetkilisi**). Birkaç dakika sonra yeşil bir onay işareti gösterilir ve **bağlantı durumu** olduğu **etkin**. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.

## <a name="create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.

   ![NavigateIntune][NavigateIntune]

2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

3. **Ayarlar**'a gidin ve daha önce içeri aktarmış olduğunuz .cer dosyası Kök CA Sertifikası'nı girin.

   > [!NOTE]
   > **Adım 3**’te seçtiğiniz platforma bağlı olarak olabilir sertifikanın **Hedef deposunu** seçebilir veya seçemeyebilirsiniz.

   ![ProfileSettings][ProfileSettings]

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
