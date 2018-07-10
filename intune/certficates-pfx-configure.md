---
title: Microsoft Intune - Azure ile PKCS sertifikalarını kullanma | Microsoft Docs
description: Kök sertifikayı dışarı aktarma, sertifika şablonunu yapılandırma, Microsoft Intune Sertifika Bağlayıcısı’nı (NDES) indirip yükleme, cihaz yapılandırma profili oluşturma, Azure’da ve Sertifika Yetkilinizde PKCS Sertifika profili oluşturma adımları da dahil olmak üzere Microsoft Intune ile Ortak Anahtar Şifreleme Standartları sertifikaları ekleyin ve oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b3bfe76173eff76a3175952bef5c6e23ad5e429
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271550"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve kullanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Sertifikalar VPN veya WiFi ağınız gibi şirket kaynaklarınıza erişimde kimlik doğrulaması yapmak ve güvenliği korumak için kullanılır. Bu makalede, PKCS sertifikasını dışarı aktarma ve ardından sertifikayı Intune profiline ekleme işlemleri gösterilir. 

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

  NDES Sertifika bağlayıcısı, Federal Bilgi İşleme Standardı (FIPS) modunu da destekler. FIPS gerekli değildir ancak etkinleştirildiğinde sertifika verebilir ve iptal edebilirsiniz.

- **Windows Server**: Microsoft Intune Sertifika Bağlayıcısı’nı (NDESConnectorSetup.exe) barındırır

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Kök sertifikayı Kurumsal CA'dan dışa aktarın

VPN, WiFi ve diğer kaynakların kimliğini doğrulamak için her cihazda bir kök veya ara CA sertifikası gereklidir. Aşağıdaki adımlar, Kurumsal CA'nızdan gerekli sertifikayı nasıl alacağınızı açıklar.

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. Yönetici olarak bir komut istemi açın.
3. Kök CA Sertifikasını (.cer), daha sonra erişebileceğiniz bir konuma dışarı aktarın.

   Örneğin:

4. Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

   `certutil -ca.cert certnew.cer`

   Daha fazla bilgi için bkz: [Sertifikaları yönetmek için Certutil görevleri](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Sertifika yetkilisinde sertifika şablonlarını yapılandırma

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. **Sertifika Yetkilisi** konsolunu açın, **Sertifika Şablonları**'na sağ tıklayın ve **Yönet**'i seçin.
3. **Kullanıcı** sertifika şablonunu bulun, sağ tıklayın ve **Yinelenen Şablon**’u seçin. **Yeni Şablon Özellikleri** açılır.
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
11. **Uygula**’yı seçin ve ardından sertifika şablonunu kaydetmek için **Tamam**’ı seçin.
12. **Sertifika Şablonları Konsolu**’nu kapatın.
13. **Sertifika Yetkilisi konsolundan**, **Sertifika Şablonları**’na sağ tıklayın, **Yeni**, **Yayımlanacak Sertifika Şablonu**’na tıklayın. Önceki adımlarda oluşturduğunuz şablonu seçin ve sonra **Tamam**’ı seçin.
14. Sunucunun, Intune kayıtlı cihazlar ve kullanıcılar adına sertifika yönetmesi için şu adımları izleyin:

    1. Sertifika Yetkilisine sağ tıklayın ve ardından **Özellikler**’i seçin.
    2. Güvenlik sekmesinde, Microsoft Intune Sertifika Bağlayıcıyı çalıştırdığınız sunucunun Bilgisayar Hesabını ekleyin. **Sertifikaları Yayımla ve Yönet** ve **Sertifikaları İste**’ye izin ver, bilgisayar hesabına izin verir.

15. Kurumsal CA'da oturumu kapatın.

## <a name="download-install-and-configure-the-certificate-connector"></a>Sertifika bağlayıcısını indirme, yükleme ve yapılandırma

![ConnectorDownload][ConnectorDownload]

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** bölmesinde **Sertifika Yetkilisi**’ni seçin.
4. **Ekle**’ye tıklayın ve **Bağlayıcı dosyasını indir**’i seçin. İndirilen dosyayı yükleyeceğiniz sunucuda erişebileceğiniz bir konuma kaydedin.
5. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. NDES Sertifika bağlayıcısının gerektirdiği .NET 4.5 Framework’ün yüklü olduğundan emin olun. .NET 4.5 Framework, Windows Server 2012 R2 ve daha yeni sürümlere otomatik olarak eklenir.
    2. Yükleyiciyi (NDESConnectorSetup.exe) çalıştırın ve varsayılan konumu kabul edin. Bağlayıcı `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe` konumuna yüklenir. Yükleyici Seçenekleri’nde **PFX Dağıtımı**’nı seçin. Devam edin ve yüklemeyi tamamlayın.

6. NDES Bağlayıcısı, **Kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**’ı seçin ve yönetim izinleri olan bir hesap girin.
7. **Gelişmiş** sekmesinde **Bu bilgisayarın SİSTEM hesabını (varsayılan) kullan**’ı seçili bırakın.
8. **Uygula**'yı ve ardından **Kapat**'ı seçin.
9. Azure portalına dönün (**Intune** > **Cihaz Yapılandırması** > **Sertifika Yetkilisi**). Birkaç dakika sonra yeşil bir onay işareti görüntülenir ve **Bağlantı durumu** **Etkin** olur. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.

> [!NOTE]
> TLS 1.2 desteği, NDES Sertifika Bağlayıcısına dahil edilmiştir. Bu nedenle NDES Sertifika bağlayıcısı yüklü olan sunucu TLS 1.2’yi destekliyorsa TLS 1.2 kullanılır. Sunucu TLS 1.2 desteklemiyorsa TLS 1.1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

## <a name="create-a-device-configuration-profile"></a>Bir cihaz yapılandırma profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.

   ![NavigateIntune][NavigateIntune]

3. Aşağıdaki özellikleri girin:

  - Profil için **Ad**
  - İsteğe bağlı olarak bir açıklama ayarlayın
  - Profili dağıtmak için **Platform**
  - **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

4. **Ayarlar**'a gidin ve daha önce içeri aktarmış olduğunuz .cer dosyası Kök CA Sertifikası'nı girin.

   > [!NOTE]
   > **Adım 3**’te seçtiğiniz platforma bağlı olarak olabilir sertifikanın **Hedef deposunu** seçebilir veya seçemeyebilirsiniz.

   ![ProfileSettings][ProfileSettings]

5. **Tamam**’ı ve ardından profilinizi kaydetmek için **Oluştur**’u seçin.
6. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS Sertifika profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.
3. Aşağıdaki özellikleri girin:

  - Profil için **Ad**
  - İsteğe bağlı olarak bir açıklama ayarlayın
  - Profili dağıtmak için **Platform**
  - **Profil türü**’nü **PKCS sertifika** olarak ayarlayın

4. **Ayarlar**'a gidin ve aşağıdaki özellikleri girin:

  - **Yenileme eşiği (%)** - 20% önerilir.
  - **Sertifika geçerlilik süresi** - Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanabilir.
  - **Sertifika yetkilisi** -Kurumsal CA'nın dahili tam etki alanı adını (FQDN) görüntüler.
  - **Sertifika yetkilisi adı** - Bu Kurumsal CA'nızın adını listeler ve önceki öğeden farklı olabilir.
  - **Sertifika şablonu adı** - Daha önce oluşturduğunuz şablonun adı. **Şablon adı**’nın varsayılan olarak **Şablon görüntü adı** ile *boşluksuz* aynı olduğunu unutmayın.
  - **Konu adı biçimi** - Aksi gerekmedikçe, bu seçeneği **Ortak ad** olarak ayarlayın.
  - **Konu alternatif adı** - Aksi gerekmedikçe, bu seçeneği **Kullanıcı asıl adı (UPN)** olarak ayarlayın.
  - **Genişletilmiş anahtar kullanımı** - [Sertifika yetkilisinde sertifika şablonlarını yapılandırma](#configure-certificate-templates-on-the-certification-authority) bölümündeki (bu makalede) 10. Adım'da varsayılan ayarları kullandıysanız, seçimden aşağıdaki **Önceden tanımlı değerler**’i ekleyin:
    - **Herhangi Bir Amaç**
    - **İstemci Kimlik Doğrulaması**
    - **Güvenli E-posta**
  - **Kök Sertifika** - (Android Profilleri için) [Kök sertifikayı Kurumsal CA'dan dışa aktarma](#export-the-root-certificate-from-the-enterprise-ca) bölümündeki (bu makalede) 3. Adım'da dışa aktarılan .cer dosyasıdır.

5. **Tamam**’ı ve ardından profilinizi kaydetmek için **Oluştur**’u seçin.
6. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="next-steps"></a>Sonraki adımlar
[SCEP sertifikalarını kullanma](certificates-scep-configure.md) veya [Symantec PKI yöneticisi web hizmetinden PKCS sertifikaları verme](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Azure portalında Intune'a gidin ve güvenilen bir sertifika için yeni bir profil oluşturun"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Bir profili oluşturun ve güvenilen bir sertifika yükleyin"
[ConnectorDownload]: ./media/certificates-download-connector.png "Azure portalından sertifika bağlayıcıyı indirin"  
