---
title: "Microsoft Intune - Azure ile PKCS sertifikalarını kullanma | Microsoft Docs"
description: "Kök sertifikayı dışarı aktarma, sertifika şablonunu yapılandırma, Microsoft Intune Sertifika Bağlayıcısı'nı indirip yükleme, cihaz yapılandırma profili oluşturma, Azure'da ve Sertifika Yetkilinizde PKCS Sertifika profili oluşturma adımları da dahil olmak üzere Microsoft Intune ile Ortak Anahtar Şifreleme Standartları sertifikaları ekleyin ve oluşturun"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c0668921f03b24b319c2c37837dbd2cc053370ca
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve kullanma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sertifikalar VPN veya WiFi ağınız gibi şirket kaynaklarınıza erişimde kimlik doğrulaması yapmak ve güvenliği korumak için kullanılır. Bu makalede, PKCS sertifikasını dışarı aktarma ve ardından sertifikayı Intune profiline ekleme işlemleri gösterilir. 

## <a name="requirements"></a>Gereksinimler

PKCS sertifikalarını Intune ile kullanmak için aşağıdaki altyapıya sahip olduğunuzdan emin olun:

* Var olan bir Active Directory Etki Alanı Hizmetleri (AD DS) etki alanı yapılandırıldı.
 
  AD DS'yi yükleme ve yapılandırma hakkında daha fazla bilgi için bkz. [AD DS Tasarımı ve Planlaması](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Var olan bir Kurumsal Sertifika Yetkilisi (CA) yapılandırıldı.

  Active Directory Sertifika Hizmetleri'ni (AD CS) yükleme ve yapılandırma hakkında daha fazla bilgi için bkz. [Active Directory Sertifika Hizmetleri Adım Adım Kılavuzu](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune, AD CS'yi, Tek Başına bir CA yerine bir Kurumsal Sertifika Yetkilisi (CA) ile çalıştırmanızı gerektirir.

* Kurumsal CA'ya bağlantı olan bir istemci.
* Kök sertifikanızın Kurumsal CA'ndan dışa aktarılmış bir kopyası.
* Intune portalınızdan indirilen Microsoft Intune Sertifika Bağlayıcı (NDESConnectorSetup.exe).
* Microsoft Intune Sertifika Bağlayıcısı'nı (NDESConnectorSetup.exe) barındıracak Windows Server.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Kök sertifikayı Kurumsal CA'dan dışa aktarın

VPN, WiFi ve diğer kaynakların kimliğini doğrulamak için, her cihazda bir kök veya ara CA sertifikası gereklidir. Aşağıdaki adımlar, Kurumsal CA'nızdan gerekli sertifikayı nasıl alacağınızı açıklar.

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. Yönetici olarak bir komut istemi açın.
3. Kök CA Sertifikasını (.cer), daha sonra erişebileceğiniz bir konuma dışarı aktarın.

   Örneğin:

4.  Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

   `certutil -ca.cert certnew.cer`

   Daha fazla bilgi için bkz: [Sertifikaları yönetmek için Certutil görevleri](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Sertifika yetkilisinde sertifika şablonlarını yapılandırma

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. **Sertifika Yetkilisi** konsolunu açın, **Sertifika Şablonları**'na sağ tıklayın ve **Yönet**'i seçin.
3. **Kullanıcı** sertifika şablonunu bulun, sağ tıklayın ve **Yinelenen Şablon**’u seçin. **Yeni Şablon Özellikleri** açılır.
4. **Uyumluluk** sekmesinde: 
   * **Sertifika Yetkilisi**’ni **Windows Server 2008 R2**’ye ayarlayın
   * **Sertifika alıcısını**’nı **Windows Server 7/ 2008 R2**’ye ayarlayın
5. **Genel** sekmesinde:
   * **Şablon görünen adı**’nı sizin için anlamlı bir şey yapın.

   > [!WARNING]
   > **Şablon adı** varsayılan olarak **şablon görünen adı** ile *boşluksuz* aynıdır. Şablon adını not alın çünkü daha sonra gerekecektir.

6. **İstek İşleme**'de **Özel anahtar dışarı aktarılabilsin**'i seçin.
7. **Şifreleme**'de **En az anahtar boyutu**’nun 2048 olarak ayarlandığını onaylayın.
8. **Konu Adı**'nda **İstekte sağla**'yı seçin.
9. **Uzantılar**'da, **Uygulama İlkeleri** altında Şifreleme Dosya Sistemi, Güvenli E-posta ve İstemci Kimlik Doğrulamasını gördüğünüzü onaylayın.
    
      > [!IMPORTANT]
      > iOS ve macOS sertifika şablonları için, **Uzantılar** sekmesine gidin, **Anahtar Kullanımı**'nı güncelleştirin ve **İmza kaynağın delilidir** öğesinin seçili olmadığını onaylayın.

10. **Güvenlik**'te, Microsoft Intune Sertifika Bağlayıcı yüklediğiniz sunucunun Bilgisayar Hesabını ekleyin.
    * Bu hesabın izinleri **Okuma** ve **Kaydetme**’sine izin verin.
11. **Uygula**’yı seçin ve ardından sertifika şablonunu kaydetmek için **Tamam**’ı seçin.
12. **Sertifika Şablonları Konsolu**’nu kapatın.
13. **Sertifika Yetkilisi konsolundan**, **Sertifika Şablonları**’na sağ tıklayın, **Yeni**, **Yayımlanacak Sertifika Şablonu**’na tıklayın.
    * Önceki adımlarda oluşturduğunuz şablonu seçin ve sonra da **Tamam**’ı seçin.
14. Sunucunun, Intune kayıtlı cihazlar ve kullanıcılar adına sertifika yönetmesi için şu adımları izleyin:

    a. Sertifika Yetkilisine sağ tıklayın ve ardından **Özellikler**’i seçin.

    b. Güvenlik sekmesinde, Microsoft Intune Sertifika Bağlayıcıyı çalıştırdığınız sunucunun Bilgisayar Hesabını ekleyin.
      * **Sertifikaları Yayımla ve Yönet** ve **Sertifikaları İste**’ye izin ver, bilgisayar hesabına izin verir.
15. Kurumsal CA'da oturumu kapatın.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Microsoft Intune Exchange Bağlayıcı'yı İndirme, Yükleme ve Yapılandırma

![ConnectorDownload][ConnectorDownload]

1. [Azure portalında](https://portal.azure.com), **Tüm hizmetler**’i seçin ve **Intune** için filtre uygulayın. **Microsoft Intune**’u seçin ve sonra da **Cihaz Yapılandırması**’nı seçin. 
2. **Sertifika Yetkilisi**'ni, **Ekle**'yi ve sonra da **Bağlayıcı dosyasını indir**'i seçin. İndirilen dosyayı, onun yükleneceği sunucudan erişebileceğiniz bir konuma kaydedin. 
3. Bu sunucuda oturum açın ve yükleyiciyi çalıştırın: 

    1. Varsayılan konumu kabul edin. Bağlayıcı `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe` konumuna yüklenir.
    2. Yükleyici Seçenekleri'nde **PFX Dağıtımı**'nı ve ardından **İleri**'yi seçin.
    3. **Yükle**'yi seçin ve yüklemenin tamamlanmasını bekleyin.
    4. Tamamlandığında, **Intune Bağlayıcısı'nı Başlat**'ı işaretleyin ve **Son**'u seçin.

4. NDES Bağlayıcı penceresinin **Kayıt** sekmesi açılmalıdır. Intune bağlantısını etkinleştirmek için **Oturum Aç**’ı seçin ve yönetim izinleri olan bir hesap girin.
5. **Gelişmiş** sekmesinde **Bu bilgisayarın SİSTEM hesabını (varsayılan) kullan**’ı seçili bırakın.
6. **Uygula**'yı ve ardından **Kapat**'ı seçin.
7. Azure portalına dönün (**Intune** > **Cihaz Yapılandırması** > **Sertifika Yetkilisi**). Birkaç dakika sonra yeşil bir onay işareti görüntülenir ve **Bağlantı durumu** **Etkin** olur. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.

## <a name="create-a-device-configuration-profile"></a>Bir cihaz yapılandırma profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Intune**, **Cihaz yapılandırması**, **Profiller**’e gidin ve **Profil oluştur**’u seçin.

   ![NavigateIntune][NavigateIntune]

3. Aşağıdaki özellikleri girin:
   * Profil için **Ad**
   * İsteğe bağlı olarak bir açıklama ayarlayın
   * Profili dağıtmak için **Platform**
   * **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

4. **Ayarlar**'a gidin ve daha önce içeri aktarmış olduğunuz .cer dosyası Kök CA Sertifikası'nı girin.

   > [!NOTE]
   > **Adım 3**’te seçtiğiniz platforma bağlı olarak olabilir sertifikanın **Hedef deposunu** seçebilir veya seçemeyebilirsiniz.

   ![ProfileSettings][ProfileSettings]

5. **Tamam**’ı ve ardından profilinizi kaydetmek için **Oluştur**’u seçin.
6. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS Sertifika profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Intune**, **Cihaz yapılandırması**, **Profiller**’e gidin ve **Profil oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:
   * Profil için **Ad**
   * İsteğe bağlı olarak bir açıklama ayarlayın
   * Profili dağıtmak için **Platform**
   * **Profil türü**’nü **PKCS sertifika** olarak ayarlayın
4. **Ayarlar**'a gidin ve aşağıdaki özellikleri girin:
   * **Yenileme eşiği (%)** - 20% önerilir.
   * **Sertifika geçerlilik süresi** - Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanabilir.
   * **Sertifika yetkilisi** -Kurumsal CA'nın dahili tam etki alanı adını (FQDN) görüntüler.
   * **Sertifika yetkilisi adı** - Bu Kurumsal CA'nızın adını listeler ve önceki öğeden farklı olabilir.
   * **Sertifika şablonu adı** - Daha önce oluşturduğunuz şablonun adı. **Şablon adı**’nın varsayılan olarak **Şablon görüntü adı** ile *boşluksuz* aynı olduğunu unutmayın.
   * **Konu adı biçimi** - Aksi gerekmedikçe, bu seçeneği **Ortak ad** olarak ayarlayın.
   * **Konu alternatif adı** - Aksi gerekmedikçe, bu seçeneği **Kullanıcı asıl adı (UPN)** olarak ayarlayın.
   * **Genişletilmiş anahtar kullanımı** - [Sertifika yetkilisinde sertifika şablonlarını yapılandırma](#configure-certificate-templates-on-the-certification-authority) bölümündeki (bu makalede) 10. Adım'da varsayılan ayarları kullandıysanız, seçimden aşağıdaki **Önceden tanımlı değerler**’i ekleyin:
      * **Herhangi Bir Amaç**
      * **İstemci Kimlik Doğrulaması**
      * **Güvenli E-posta**
   * **Kök Sertifika** - (Android Profilleri için) [Kök sertifikayı Kurumsal CA'dan dışa aktarma](#export-the-root-certificate-from-the-enterprise-ca) bölümündeki (bu makalede) 3. Adım'da dışa aktarılan .cer dosyasıdır.

5. **Tamam**’ı ve ardından profilinizi kaydetmek için **Oluştur**’u seçin.
6. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profilleri nasıl atanır](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Azure portalında Intune'a gidin ve güvenilen bir sertifika için yeni bir profil oluşturun"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Bir profili oluşturun ve güvenilen bir sertifika yükleyin"
[ConnectorDownload]: ./media/certificates-download-connector.png "Azure portalından sertifika bağlayıcıyı indirin"  
