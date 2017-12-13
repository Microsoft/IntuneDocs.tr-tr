---
title: "Intune ile PKCS sertifikalarını yapılandırma ve yönetme"
titleSuffix: Intune on Azure
description: "Intune ile PKCS sertifikaları oluşturun ve atayın. \""
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 11/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 105b5fc73bc537eaca67a0e6943701ba25a53972
ms.sourcegitcommit: 2b35c99ca7d3dbafe2dfe1e0b9de29573db403b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/16/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve yönetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a>Gereksinimler

PKCS sertifikalarını Intune ile kullanmak için aşağıdaki altyapıya sahip olmanız gerekir:

* Var olan bir Active Directory Etki Alanı Hizmetleri (AD DS) etki alanı yapılandırıldı.
 
  AD DS'yi yükleme ve yapılandırma hakkında daha fazla bilgiye ihtiyacınız varsa, [AD DS Tasarımı ve Planlaması](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning) makalesine bakın.

* Var olan bir Kurumsal Sertifika Yetkilisi (CA) yapılandırıldı.

  Active Directory Sertifika Hizmetlerini (AD CS) yükleme ve yapılandırma hakkında daha fazla bilgiye ihtiyacınız varsa, [Active Directory Sertifika Hizmetleri Adım Adım Kılavuzu](https://technet.microsoft.com/library/cc772393) makalesine bakın.

  > [!WARNING]
  > Intune, AD CS'yi, Tek Başına bir CA yerine bir Kurumsal Sertifika Yetkilisi (CA) ile çalıştırmanızı gerektirir.

* Kurumsal CA'ya bağlantı olan bir istemci.
* Kök sertifikanızın Kurumsal CA'ndan dışa aktarılmış bir kopyası.
* Intune Portal'ınızdan indirilen Microsoft Intune Sertifika Bağlayıcı (NDESConnectorSetup.exe).
* Microsoft Intune Sertifika Bağlayıcı’yı (NDESConnectorSetup.exe) barındırabilen Windows Server.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Kök sertifikayı Kurumsal CA'dan dışa aktarın

VPN, WiFi ve diğer kaynaklarla kimlik doğrulama yapmak için her cihazda bir kök veya ara CA sertifikasına ihtiyacınız vardır. Aşağıdaki adımlar, Kurumsal CA'nızdan gerekli sertifikayı nasıl alacağınızı açıklar.

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. Yönetici olarak bir komut istemi açın.
3. Kök CA Sertifikasını, daha sonra erişebileceğiniz bir konuma dışarı aktarın.

   Örneğin:

   `certutil -ca.cert certnew.cer`

   Daha fazla bilgi için bkz: [Sertifikaları yönetmek için Certutil görevleri](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).


## <a name="configure-certificate-templates-on-the-certification-authority"></a>Sertifika yetkilisinde sertifika şablonlarını yapılandırma

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. **Sertifika Yetkilisi** konsolunu açın.
3. **Sertifika Şablonları**’na sağ tıklayın, sonra da **Yönet**’i seçin.
4. **Kullanıcı** sertifika şablonunu bulun, sağ tıklayın ve **Yinelenen Şablon**’u seçin. Bir pencere açılır, **Yeni Şablon Özellikleri**.
5. **Uyumluluk** sekmesinde
   * **Sertifika Yetkilisi**’ni **Windows Server 2008 R2**’ye ayarlayın
   * **Sertifika alıcısını**’nı **Windows Server 7/ 2008 R2**’ye ayarlayın
6. **Genel** sekmesinde:
   * **Şablon görünen adı**’nı sizin için anlamlı bir şey yapın.

   > [!WARNING]
   > **Şablon adı** varsayılan olarak **şablon görünen adı** ile *boşluksuz* aynıdır. Daha sonra kullanmak için şablon adını not edin.

7. **İstek İşleme** sekmesinde **Özel anahtar dışarı aktarılabilsin**'i kontrol edin.
8. **Şifreleme** sekmesinde, **En az anahtar boyutu**’nun 2048 olarak ayarlandığını onaylayın.
9. **Konu Adı** sekmesinde, radyo düğmesini **İstekte tedarik** olarak seçin.
10. **Uzantılar** sekmesinde, **Uygulama İlkeleri** altında Şifreleme Dosya Sistemi, Güvenli E-posta ve İstemci Kimlik Doğrulamasını gördüğünüzü onaylayın.
    
      > [!IMPORTANT]
      > iOS ve macOS sertifika şablonları için, **Uzantılar** sekmesinde **Anahtar Kullanımı**'nı düzenleyin ve **İmza kaynağın delilidir** öğesinin seçili olmadığından emin olun.

11. **Güvenlik** sekmesinde, Microsoft Intune Sertifika Bağlayıcı yüklediğiniz sunucunun Bilgisayar Hesabını ekleyin.
    * Bu hesabın izinleri **Okuma** ve **Kaydetme**’sine izin verin.
12. **Uygula**’ya tıklayın ardından sertifika şablonunu kaydetmek için **Tamam**’a tıklayın.
13. **Sertifika Şablonları Konsolu**’nu kapatın.
14. **Sertifika Yetkilisi konsolundan**, **Sertifika Şablonları**’na sağ tıklayın, **Yeni**, **Yayımlanacak Sertifika Şablonu**’na tıklayın.
    * Önceki adımlarda oluşturduğunuz şablonu seçin ve **Tamam**’a tıklayın.
15. Sunucunun, Intune kayıtlı cihazlar ve kullanıcılar adına sertifika yönetmesi için şu adımları izleyin:

    a. Sertifika Yetkilisine sağ tıklayın ve ardından **Özellikler**’i seçin.

    b. Güvenlik sekmesinde, Microsoft Intune Sertifika Bağlayıcıyı çalıştırdığınız sunucunun Bilgisayar Hesabını ekleyin.
      * **Sertifikaları Yayımla ve Yönet** ve **Sertifikaları İste**’ye izin ver, bilgisayar hesabına izin verir.
16. Kurumsal CA'da oturumu kapatın.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Microsoft Intune Exchange Bağlayıcı'yı İndirme, Yükleme ve Yapılandırma

![ConnectorDownload][ConnectorDownload]

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Intune**, **Cihaz yapılandırması**, **Sertifika Yetkilisi**’ne gidin ve **Sertifika Bağlayıcı’yı indir**’e tıklayın.
   * İndirmeyi, onu yükleyeceğiniz sunucuda erişebileceğiniz bir konuma kaydedin.
3. Microsoft Intune Sertifika Bağlayıcı’yı yükleyeceğiniz sunucuda oturum açın.
4. Yükleyiciyi çalıştırın ve varsayılan konumu kabul edin. Bağlayıcıyı C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe konumuna yükler.

      a. Yükleyici Seçenekleri sayfasında **PFX Dağıtımı**’nı seçin ve **İleri**’ye tıklayın.

   b. **Yükle**’ye tıklayın ve yüklemenin tamamlanmasını bekleyin.

   c. Tamamlama sayfasında **Intune Bağlayıcı’yı Başlat** etiketli kutunun seçili olduğunu kontrol edin ve **Son**’a tıklayın.

5. NDES Bağlayıcı penceresi şimdi **Kayıt** sekmesine açılmalıdır. Intune bağlantısını etkinleştirmek için **Oturum Aç**’a tıklamalı ve yönetimsel izinleri olan bir hesap sağlamalısınız.
6. **Gelişmiş** sekmesinde, radyo düğmesini **Bu bilgisayarın SİSTEM hesabını (varsayılan) kullan**’ı seçili bırakabilirsiniz.
7. **Uygula**’ya tıklayın ardından **Kapat**.
8. Şimdi Azure portalına geri gidin. **Intune**, **Cihaz yapılandırması**, **Sertifika Yetkilisi** altında yeşil onay işareti ve birkaç dakika sonra **Bağlantı durumu** altında **Etkin** kelimesini görmeniz gerekir. Bu onay, bağlayıcı sunucunuzun Intune ile iletişim kurabildiğini bilmenizi sağlar.

## <a name="create-a-device-configuration-profile"></a>Bir cihaz yapılandırma profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Intune**, **Cihaz yapılandırması**, **Profiller**’e gidin ve **Profil oluştur**’a tıklayın.

   ![NavigateIntune][NavigateIntune]

3. Aşağıdaki bilgileri doldurun:
   * Profil için **Ad**
   * İsteğe bağlı olarak bir açıklama ayarlayın
   * Profili dağıtmak için **Platform**
   * **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın
4. **Ayarlar**’a gidin ve Kök CA sertifikasının önceden dışarı aktardığı .cer dosyasını sağlayın.

   > [!NOTE]
   > **Adım 3**’te seçtiğiniz platforma bağlı olarak olabilir sertifikanın **Hedef deposunu** seçme seçeneğiniz olabilir veya olmayabilir.

   ![ProfileSettings][ProfileSettings]

5. **Tamam**’a tıklayın ardından profilinizi kaydetmek için **Oluştur**’a tıklayın.
6. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profilleri nasıl atanır](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS Sertifika profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Intune**, **Cihaz yapılandırması**, **Profiller**’e gidin ve **Profil oluştur**’a tıklayın.
3. Aşağıdaki bilgileri doldurun:
   * Profil için **Ad**
   * İsteğe bağlı olarak bir açıklama ayarlayın
   * Profili dağıtmak için **Platform**
   * **Profil türü**’nü **PKCS sertifika** olarak ayarlayın
4. **Ayarlar**’a gidin ve aşağıdaki bilgileri sağlayın:
   * **Yenileme eşiği (%)** - 20% önerilir.
   * **Sertifika geçerlilik süresi** - Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanmalıdır.
   * **Sertifika yetkilisi** -Bu seçenek Kurumsal CA'nın dahili tam etki alanı adıdır (FQDN).
   * **Sertifika yetkilisi adı** - Bu seçenek Kurumsal CA'nızın adıdır ve önceki öğeden farklı olabilir.
   * **Sertifika şablonu adı** - Bu seçenek daha önce oluşturduğunuz şablonun adıdır. **Şablon adı**’nın varsayılan olarak **Şablon görüntü adı** ile *boşluksuz* aynı olduğunu unutmayın.
   * **Konu adı biçimi** - Aksi gerekmedikçe, bu seçeneği **Ortak ad** olarak ayarlayın.
   * **Konu alternatif adı** - Aksi gerekmedikçe, bu seçeneği **Kullanıcı asıl adı (UPN)** olarak ayarlayın.
   * **Genişletilmiş anahtar kullanımı** - Önceki bölümde **Sertifika yetkilisinde sertifika şablonlarını yapılandırma** bölümündeki Adım 10’da varsayılan ayarları kullandıysanız, seçim kutusunda aşağıdaki **Önceden tanımlı değerler**’i ekleyin:
      * **Herhangi Bir Amaç**
      * **İstemci Kimlik Doğrulaması**
      * **Güvenli E-posta**
   * **Kök Sertifika** - (Android Profilleri için) Bu seçenek, önceki bölümde [Kök sertifikayı Kurumsal CA'dan dışa aktarma](#export-the-root-certificate-from-the-enterprise-ca) altında Adım 3’te dışa aktarılan .cer dosyasıdır.

5. **Tamam**’a tıklayın ardından profilinizi kaydetmek için **Oluştur**’a tıklayın.
6. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profilleri nasıl atanır](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Azure portalında Intune'a gidin ve güvenilen bir sertifika için yeni bir profil oluşturun"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Bir profili oluşturun ve güvenilen bir sertifika yükleyin"
[ConnectorDownload]: ./media/certificates-pfx-configure-connector-download.png "Azure portalından sertifika bağlayıcıyı indirin"
