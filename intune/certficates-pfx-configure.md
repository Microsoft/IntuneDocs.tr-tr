---
title: Microsoft Intune - Azure ile PKCS sertifikalarını kullanma | Microsoft Docs
description: Kök sertifikayı dışarı aktarma, sertifika şablonunu yapılandırma, Microsoft Intune Sertifika Bağlayıcısı’nı (NDES) indirip yükleme, cihaz yapılandırma profili oluşturma, Azure’da ve Sertifika Yetkilinizde PKCS Sertifika profili oluşturma adımları da dahil olmak üzere Microsoft Intune ile Ortak Anahtar Şifreleme Standartları sertifikaları ekleyin ve oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573cdf8746b9eaf593a33cd943b69a2dd83030ae
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/17/2018
ms.locfileid: "49391612"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve kullanma

> [!IMPORTANT]
> S/MIME özelliğinde, bu makalede açıklanan bazı geliştirmeler yapıyoruz. Bunun sonucu olarak, S/MIME özelliği Intune'da geçici olarak kaldırıldı. Özellik kullanıma sunulduğunda bu notu kaldıracağız.

Sertifikalar VPN veya WiFi ağınız gibi şirket kaynaklarınıza erişimde kimlik doğrulaması yapar ve güvenliği korur. Bu makalede, PKCS sertifikasını dışarı aktarma ve ardından sertifikayı Intune profiline ekleme işlemleri gösterilir.

## <a name="requirements"></a>Gereksinimler

PKCS sertifikalarını Intune ile kullanmak için aşağıdaki altyapıya sahip olduğunuzdan emin olun:

- **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucular, Active Directory etki alanınıza katılmalıdır.

  AD DS'yi yükleme ve yapılandırma hakkında daha fazla bilgi için bkz. [AD DS Tasarımı ve Planlaması](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Sertifika Yetkilisi** (CA): Bir Kuruluş Sertifika Yetkilisi (CA)

  Active Directory Sertifika Hizmetleri'ni (AD CS) yükleme ve yapılandırma hakkında daha fazla bilgi için bkz. [Active Directory Sertifika Hizmetleri Adım Adım Kılavuzu](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune, AD CS'yi, Tek Başına bir CA yerine bir Kurumsal Sertifika Yetkilisi (CA) ile çalıştırmanızı gerektirir.

- **Bir istemci**: Kuruluş Sertifika Yetkilisine bağlanmak için

- **Kök sertifika**: Kök sertifikanızın Kuruluş Sertifika Yetkilisinden dışarı aktarılmış bir kopyası

- **Microsoft Intune Sertifika Bağlayıcısı**: **Sertifika Bağlayıcısı** yükleyicisini (**NDESConnectorSetup.exe**) indirmek için Azure portalını kullanın. 

  Bağlayıcı, kimlik doğrulama veya S/MIME e-posta imzalamaları için kullanılan PKCS sertifikası isteklerini işler.

  NDES Sertifika bağlayıcısı, Federal Bilgi İşleme Standardı (FIPS) modunu da destekler. FIPS gerekli değildir ancak etkinleştirildiğinde sertifika verebilir ve iptal edebilirsiniz.

- **Microsoft Intune için PFX Sertifika Bağlayıcısı**: S/MIME e-posta şifrelemesini kullanmayı planlıyorsanız, **Microsoft Intune için PFX Sertifika Bağlayıcısı** yükleyicisini (**PfxCertificateConnectorBootstrapper.exe**) Azure portalından indirebilirsiniz. Bağlayıcı, belirli bir kullanıcının S/MIME e-posta şifrelemesi için Intune’da içeri aktarılan PFX dosyalarına yönelik istekleri işler.

- **Windows Sunucusu**: Şunu barındırır:

  - Kimlik doğrulama ve S/MIME e-posta imzalama senaryoları için Microsoft Intune Sertifika Bağlayıcısı (NDESConnectorSetup.exe)
  - S/MIME e-posta şifreleme senaryoları için Microsoft Intune için PFX Sertifika Bağlayıcısı (PfxCertificateConnectorBootstrapper.exe).

  Her iki bağlayıcıyı da (**Microsoft Intune Sertifika Bağlayıcısı** ve **Microsoft Intune için PFX Sertifika Bağlayıcısı**) aynı sunucuda çalıştırabilirsiniz.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Kök sertifikayı Kurumsal CA'dan dışa aktarın

VPN, WiFi veya diğer kaynakların kimliğini doğrulamak için her cihazda bir kök veya ara CA sertifikası gereklidir. Aşağıdaki adımlar, Kurumsal CA'nızdan gerekli sertifikayı nasıl alacağınızı açıklar.

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. Yönetici olarak bir komut istemi açın.
3. Kök CA Sertifikasını (.cer), daha sonra erişebileceğiniz bir konuma dışarı aktarın.
4. Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

   `certutil -ca.cert certnew.cer`

   Daha fazla bilgi için bkz: [Sertifikaları yönetmek için Certutil görevleri](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Sertifika yetkilisinde sertifika şablonlarını yapılandırma

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. **Sertifika Yetkilisi** konsolunu açın, **Sertifika Şablonları**'na sağ tıklayın ve **Yönet**'i seçin.
3. **Kullanıcı** sertifika şablonunu bulun, şablona sağ tıklayın ve **Şablonu Yinele**’yi seçin. **Yeni Şablon Özellikleri** açılır.

    > [!NOTE]
    > S/MIME e-posta imzalama ve şifreleme senaryolarında, birçok yönetici imzalama ve şifreleme için ayrı sertifikalar kullanır. Microsoft Active Directory Sertifika Hizmetlerini kullanıyorsanız, S/MIME e-posta imzalama sertifikaları için **Yalnızca Exchange İmzası** şablonunu ve S/MIME şifreleme sertifikaları için de **Exchange Kullanıcısı** şablonunu kullanabilirsiniz.  Üçüncü taraf sertifika yetkilisi kullanıyorsanız, imzalama ve şifreleme şablonları ayarlamak için onların kendi yönergelerini gözden geçirmeniz önerilir.

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
13. Sunucunun, Intune'a kayıtlı cihazlar ve kullanıcılar adına sertifikaları yönetmesi için aşağıdaki adımları kullanın:

    1. Sertifika Yetkilisine sağ tıklayın ve ardından **Özellikler**’i seçin.
    2. Güvenlik sekmesinde, bağlayıcıları (**Microsoft Intune Sertifika Bağlayıcısı** veya **Microsoft Intune için PFX Sertifika Bağlayıcısı**) çalıştırdığınız sunucunun Bilgisayar hesabını ekleyin. **Sertifikaları Yayımla ve Yönet** ve **Sertifikaları İste**’ye izin ver, bilgisayar hesabına izin verir.

14. Kurumsal CA'da oturumu kapatın.

## <a name="download-install-and-configure-the-certificate-connectors"></a>Sertifika bağlayıcılarını indirme, yükleme ve yapılandırma

### <a name="microsoft-intune-certificate-connector"></a>Microsoft Intune Sertifika Bağlayıcısı

> [!IMPORTANT] 
> Microsoft Intune Sertifika Bağlayıcısı, ayrı bir Windows sunucusunda yüklü olmak **zorundadır**. Sertifika veren Sertifika Yetkilisi’ne (CA) yüklenemez.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
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
8. Azure portalına dönün (**Intune** > **Cihaz Yapılandırması** > **Sertifika Yetkilisi**). Birkaç dakika sonra yeşil bir onay işareti görüntülenir ve **Bağlantı durumu** **Etkin** olur. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.

> [!NOTE]
> TLS 1.2 desteği, Microsoft Intune Sertifika Bağlayıcısı'na dahil edilmiştir. Bu nedenle Microsoft Intune Sertifika Bağlayıcısı'nın yüklü olduğu sunucu TLS 1.2’yi destekliyorsa TLS 1.2 kullanılır. Sunucu TLS 1.2 desteklemiyorsa TLS 1.1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>Microsoft Intune için PFX Sertifika Bağlayıcısı

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz Yapılandırması** > **Sertifika Yetkilisi** > **Ekle**
3. Microsoft Intune için PFX Sertifika Bağlayıcısı’nı indirin ve kaydedin. Bağlayıcıyı, yükleyeceğiniz sunucudan erişilebilir bir konuma kaydedin.
4. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. Microsoft Intune için PFX Sertifika Bağlayıcısı'nın gerektirdiği .NET 4.6 Framework veya sonraki bir sürümünün yüklü olduğundan emin olun. .NET 4.6 Framework yüklü değilse yükleyici bunu otomatik olarak yükler.
    2. Yükleyiciyi (PfxCertificateConnectorBootstrapper.exe) çalıştırın ve varsayılan konumu kabul edin. Bağlayıcı `Program Files\Microsoft Intune\PFXCertificateConnector` konumuna yüklenir.
    3. Bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet erişimi için bir ara sunucu gerekiyorsa, yerel hizmet hesabının sunucudaki ara sunucu ayarlarına erişebildiğinizden emin olun.

5. Microsoft Intune için PFX Sertifika Bağlayıcısı yüklendikten sonra **Kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**'ı seçin ve Azure genel yöneticisi veya Intune yöneticisi izinleri olan bir hesap girin.
6. Pencereyi kapatın.
7. Azure portalına dönün (**Intune** > **Cihaz Yapılandırması** > **Sertifika Yetkilisi**). Birkaç dakika sonra yeşil bir onay işareti görüntülenir ve **Bağlantı durumu** **Etkin** olur. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.

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
    - **Anahtar depolama sağlayıcısı (KSP)**: Windows için, cihazdaki anahtarları nereye depolayacağınızı seçin.
    - **Sertifika yetkilisi**: Kurumsal CA'nızın dahili tam etki alanı adını (FQDN) görüntüler.
    - **Sertifika yetkilisi adı**: “Contoso Sertifika Yetkilisi” gibi Kurumsal CA'nızın adını listeler.
    - **Sertifika şablonu adı**: Daha önce oluşturduğunuz şablonun adı. **Şablon adı**’nın varsayılan olarak **Şablon görüntü adı** ile *boşluksuz* aynı olduğunu unutmayın.
    - **Konu adı biçimi**: Aksi gerekmedikçe, bu seçeneği **Ortak ad** olarak ayarlayın.
    - **Konu alternatif adı**: Aksi gerekmedikçe, bu seçeneği **Kullanıcı asıl adı (UPN)** olarak ayarlayın.

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="create-a-pkcs-imported-certificate-profile"></a>PKCS içeri aktarılmış sertifika profili oluşturma

Daha önce belirli bir kullanıcıya verilmiş olan sertifikaları herhangi bir sertifika yetkilisinden Intune’a aktarabilirsiniz. İçeri aktarılan sertifikalar, kullanıcının kaydettiği her cihaza yüklenir. S/MIME e-posta şifreleme, var olan PFX sertifikalarını Intune’a aktarmak için en yaygın kullanılan senaryodur. Kullanıcının, e-postayı şifrelemek için birden çok sertifikası olabilir. Daha önce şifrelenmiş olan e-postaların şifrelerini çözmek için kullanıcının tüm cihazlarında bu sertifikaların özel anahtarları bulunmalıdır.

Intune’a sertifika aktarmak için [GitHub’da sağlanan PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanabilirsiniz.

Sertifikaları Intune’da içeri aktardıktan sonra bir **PKCS içeri aktarılmış sertifikası** profili oluşturun ve bu profili Azure Active Directory gruplarına atayın.

1. [Azure portalında](https://portal.azure.com) **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.
2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil Türü**’nü **PKCS içeri aktarılan sertifikası** olarak ayarlayın

3. **Ayarlar**'a gidin ve aşağıdaki özellikleri girin:

    - **Kullanım amacı**: Bu profil için içeri aktarılan sertifikaların kullanım amacı. Yöneticinin, farklı amaçlara (kimlik doğrulaması, S/MIME imzalaması veya S/MIME şifrelemesi gibi) yönelik içeri aktarılmış sertifikaları olabilir. Sertifika profilinde seçilen kullanım amacı, sertifika profilini doğru içeri aktarılmış sertifikalarla eşleştirir.
    - **Sertifika geçerlilik süresi**: Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanabilir.
    - **Anahtar depolama sağlayıcısı (KSP)**: Windows için, cihazdaki anahtarları nereye depolayacağınızı seçin.

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="next-steps"></a>Sonraki adımlar
[SCEP sertifikalarını kullanma](certificates-scep-configure.md) veya [Symantec PKI yöneticisi web hizmetinden PKCS sertifikaları verme](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Azure portalında Intune'a gidin ve güvenilen bir sertifika için yeni bir profil oluşturun"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Bir profili oluşturun ve güvenilen bir sertifika yükleyin"
[ConnectorDownload]: ./media/certificates-download-connector.png "Azure portalından sertifika bağlayıcıyı indirin"  
