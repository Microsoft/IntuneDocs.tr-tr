---
title: Microsoft Intune - Azure’da sertifika profilleri oluşturma | Microsoft Docs
description: Microsoft Intune ile Basit Sertifika Kayıt Protokolü (SCEP) veya ortak anahtar şifreleme standartları (PKCS) sertifikaları ve sertifika profillerini kullanma hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5092fa37f0bf6bd1320fa06fa58ac5e36f55aa3c
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410198"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Microsoft Intune kimlik doğrulaması için sertifikaları kullanma

VPN, Wi-Fi veya e-posta profilleri aracılığıyla kullanıcılarınızın uygulamalar ve Şirket kaynakları için kimlik doğrulaması yapmak üzere Intune ile sertifikaları kullanın. Bu bağlantıların kimliğini doğrulamak için sertifikaları kullandığınızda, son kullanıcılarınızın erişimleri sorunsuz hale getirmek için Kullanıcı adları ve parolalar girmesi gerekmez. Sertifikalar Ayrıca, S/MIME kullanarak e-posta imzalama ve şifreleme için de kullanılır.

## <a name="intune-supported-certificates-and-usage"></a>Intune tarafından desteklenen sertifikalar ve kullanım

| Tür              | Kimlik doğrulama | S/MIME Imzalama | S/MIME şifrelemesi  |
|--|--|--|--|
| Ortak anahtar şifreleme standartları (PKCS) içeri aktarılan sertifika |  | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png)|
| PKCS#12 (veya PFX)    | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) |  |
| Basit Sertifika Kayıt Protokolü (SCEP)  | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | |

Bu sertifikaları dağıtmak için cihazlara sertifika profilleri oluşturup atayacaksınız.

Oluşturduğunuz her ayrı sertifika profili tek bir platformu destekler. Örneğin, PKCS sertifikaları kullanıyorsanız, Android için PKCS sertifika profili ve iOS için ayrı bir PKCS sertifika profili oluşturacaksınız. Bu iki platform için SCEP sertifikaları da kullanıyorsanız, Android için bir SCEP sertifika profili ve iOS için başka bir tane oluşturun.

### <a name="general-considerations-when-you-use-a-microsoft-certification-authority"></a>Bir Microsoft sertifika yetkilisi kullanırken Genel hususlar

Bir Microsoft sertifika yetkilisi (CA) kullandığınızda:

- SCEP sertifika profillerini kullanmak için, Intune ile kullanmak üzere [bir ağ cihazı kayıt hizmeti (NDES) sunucusu ayarlamanız](certificates-scep-configure.md#set-up-ndes) gerekir.
- Aşağıdaki sertifika profili türlerini kullanmak için [Microsoft Intune sertifika Bağlayıcısı yüklemelisiniz](certificates-scep-configure.md#install-the-intune-certificate-connector):
  - SCEP sertifika profili
  - PKCS sertifika profili

- PKCS içeri aktarılan sertifikalarını kullanmak için:
  - [Microsoft Intune IÇIN PFX Sertifika bağlayıcısını yükler](certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).
  - Sertifikaları sertifika yetkilisinden dışarı aktarın ve ardından Microsoft Intune içeri aktarın. Bkz. [Pfxımport PowerShell projesi](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

- Aşağıdaki mekanizmaları kullanarak sertifikaları dağıtın:
  - Kök veya ara (veren) CA 'dan cihazlara güvenilen kök CA sertifikası dağıtmaya yönelik [Güvenilen sertifika profilleri](certificates-configure.md#create-trusted-certificate-profiles)
  - SCEP sertifika profilleri
  - PKCS sertifika profilleri
  - PKCS içeri aktarılan sertifika profilleri

### <a name="general-considerations-when-you-use-a-third-party-certification-authority"></a>Üçüncü taraf sertifika yetkilisini kullanırken Genel hususlar

Üçüncü taraf (Microsoft dışı) sertifika yetkilisi (CA) kullandığınızda:

- SCEP sertifika profillerini kullanmak için:
  - [Desteklenen iş ortaklarımızın birinden bir](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners)üçüncü taraf CA ile tümleştirmeyi ayarlayın. Kurulumu, üçüncü taraf CA 'dan gelen ve Intune ile CA tümleştirmesini tamamlamaya yönelik yönergeleri izleyerek içerir.
  - [Azure AD 'de,](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration) SCEP sertifikası sınama doğrulaması yapmak için Intune 'a haklar veren bir uygulama oluşturun.

- PKCS içeri aktarılan Sertifikalar [, Microsoft Intune IÇIN PFX Sertifika bağlayıcısını yüklemenizi](certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune)gerektirir.

- Aşağıdaki mekanizmaları kullanarak sertifikaları dağıtın:
  - Kök veya ara (veren) CA 'dan cihazlara güvenilen kök CA sertifikası dağıtmaya yönelik [Güvenilen sertifika profilleri](certificates-configure.md#create-trusted-certificate-profiles)
  - SCEP sertifika profilleri
  - PKCS sertifika profilleri *(yalnızca [DigiCert PKI platformunda](certificates-digicert-configure.md)desteklenir)*
  - PKCS içeri aktarılan sertifika profilleri

## <a name="supported-platforms-and-certificate-profiles"></a>Desteklenen platformlar ve sertifika profilleri

| Platfveyam              | Güvenilen sertifika profili | PKCS sertifika profili | SCEP sertifika profili | PKCS içeri aktarılan sertifika profili  |
|--|--|--|--|---|
| Android Cihaz Yöneticisi | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png)|  ![Desteklenir](./media/certificates-configure/green-check.png) |
| Android Kurumsal <br> -Tam olarak yönetilen (cihaz sahibi)   | ![Desteklenir](./media/certificates-configure/green-check.png) |   | ![Desteklenir](./media/certificates-configure/green-check.png) |   |
| Android Kurumsal <br> -Adanmış (cihaz sahibi)   | ![Desteklenir](./media/certificates-configure/green-check.png)  |   | ![Desteklenir](./media/certificates-configure/green-check.png)  |   |
| Android Kurumsal <br> -İş profili    | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) |
| iOS                   | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) |
| Mac OS                 | ![Desteklenir](./media/certificates-configure/green-check.png) |  ![Desteklenir](./media/certificates-configure/green-check.png) |![Desteklenir](./media/certificates-configure/green-check.png)|![Desteklenir](./media/certificates-configure/green-check.png)|
| WVPN profillerinidows Phone 8.1     |![Desteklenir](./media/certificates-configure/green-check.png)  |  | ![Desteklenir](./media/certificates-configure/green-check.png)| ![Desteklenir](./media/certificates-configure/green-check.png) |
| Windows 8.1 ve üzeri |![Desteklenir](./media/certificates-configure/green-check.png)  |  |![Desteklenir](./media/certificates-configure/green-check.png) |   |
| Windows 10 ve üzeri  | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Güvenilen kök CA sertifikasını dışarı aktarma

PKCS, SCEP ve PKCS içeri aktarılan sertifikaları kullanmak için cihazların kök sertifika yetkilinizle güvenmesi gerekir. Güven oluşturmak için, güvenilen kök CA sertifikasını ve tüm ara veya sertifika verme yetkilisi sertifikalarını ortak bir sertifika (. cer) olarak dışarı aktarın. Bu sertifikaları, veren CA 'dan veya veren CA 'nıza güvenen herhangi bir cihazdan alabilirsiniz.

Sertifikayı dışarı aktarmak için, sertifika yetkilinizin belgelerine bakın. Ortak sertifikayı bir. cer dosyası olarak dışarı aktarmanız gerekir.  Bir. pfx dosyası olan özel anahtarı dışarı aktarmayın.

Bu. cer dosyasını, bu sertifikayı cihazlarınıza dağıtmak için [Güvenilen sertifika profilleri oluştururken](#create-trusted-certificate-profiles) kullanacaksınız.

## <a name="create-trusted-certificate-profiles"></a>Güvenilen sertifika profilleri oluşturma

Bir SCEP, PKCS veya PKCS içeri aktarılan sertifika profili oluşturabilmeniz için önce bir güvenilen sertifika profili oluşturun. Güvenilen bir sertifika profili dağıtmak, her bir cihazın CA 'nızın yasallığını tanımasını sağlar. SCEP sertifika profilleri doğrudan bir güvenilen sertifika profiline başvurur. PKCS sertifika profilleri, güvenilen sertifika profiline doğrudan başvurmazlar, ancak CA 'nizi barındıran sunucuya doğrudan başvurur. PKCS içeri aktarılan sertifika profilleri güvenilen sertifika profiline doğrudan başvurmazlar, ancak bunu cihazda kullanabilir. Güvenilen bir sertifika profilinin cihazlara dağıtımı, bu güvenin kurulabilmesini sağlar. Bir cihaz kök CA 'ya güvenmezse, SCEP veya PKCS sertifika profili ilkesi başarısız olur.

Desteklemek istediğiniz her cihaz platformu için, SCEP, PKCS ve PKCS içeri aktarılan sertifika profillerinde yaptığınız gibi ayrı bir güvenilen sertifika profili oluşturun.

### <a name="to-create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturmak için

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

   ![Intune 'a gidin ve güvenilen bir sertifika için yeni bir profil oluşturun](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Aşağıdaki özellikleri girin:

   - Profil için **Ad**
   - İsteğe bağlı olarak bir **Açıklama** ayarlayın
   - Profili dağıtmak için **Platform**
   - **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

4. **Ayarlar**' ı seçin ve ardından bu sertifika profiliyle birlikte kullanmak üzere verdiğiniz GÜVENILEN kök CA sertifikası. cer dosyasına gidin ve ardından **Tamam**' ı seçin.

5. Yalnızca Windows 8.1 ve Windows 10 cihazları için, güvenilen sertifika için **Hedef Depo** olarak şunlardan birini seçin:

   - **Bilgisayar sertifika deposu - Kök**
   - **Bilgisayar sertifika deposu - Ara**
   - **Kullanıcı sertifika deposu - Ara**

6. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** bölmesine gidin ve **Oluştur**’u seçin.

Profil, *cihazlar-yapılandırma profilleri* penceresindeki profiller listesinde, **Güvenilen sertifika**profil türü ile görüntülenir. Bu profili SCEP veya PKCS sertifikaları kullanacak cihazlara atadığınızdan emin olun. Profili gruplara atamak için bkz. [cihaz profilleri atama](../configuration/device-profile-assign.md).

> [!NOTE]
> Android cihazlarda, üçüncü tarafın güvenilen bir sertifika yüklediği bir ileti görüntülenebilir.

## <a name="additional-resources"></a>Ek kaynaklar

- [Cihaz profillerini atama](../configuration/device-profile-assign.md)  
- [E-postaları imzalamak ve şifrelemek için S/MIME kullanma](certificates-s-mime-encryption-sign.md)  
- [Üçüncü taraf sertifika yetkilisini kullanma](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Sonraki adımlar

Kullanmak istediğiniz her platform için SCEP, PKCS veya PKCS içeri aktarılmış sertifika profilleri oluşturun. Devam etmek için aşağıdaki makalelere bakın:

- [Intune ile SCEP sertifikalarını destekleyecek altyapıyı yapılandırma](certificates-scep-configure.md)  
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)  
- [PKCS içeri aktarılan sertifika profili oluşturma](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)
