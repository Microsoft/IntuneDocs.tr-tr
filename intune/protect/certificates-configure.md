---
title: Microsoft Intune - Azure’da sertifika profilleri oluşturma | Microsoft Docs
description: Learn about using Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standards (PKCS) certificates and certificate profiles with Microsoft Intune.
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
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Use certificates for authentication in Microsoft Intune

Use certificates with Intune to authenticate your users to applications and corporate resources through VPN, Wi-Fi, or email profiles. When you use certificates to authenticate these connections, your end users won't need to enter usernames and passwords, which can make their access seamless. Certificates are also used for signing and encryption of email using S/MIME.

## <a name="intune-supported-certificates-and-usage"></a>Intune supported certificates and usage

| Tür              | Kimlik doğrulama | S/MIME Signing | S/MIME encryption  |
|--|--|--|--|
| Public Key Cryptography Standards (PKCS) imported certificate |  | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png)|
| PKCS#12 (veya PFX)    | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) |  |
| Basit Sertifika Kayıt Protokolü (SCEP)  | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | |

To deploy these certificates, you’ll create and assign certificate profiles to devices.

Each individual certificate profile you create supports a single platform. For example, if you use PKCS certificates, you’ll create PKCS certificate profile for Android and a separate PKCS certificate profile for iOS. If you also use SCEP certificates for those two platforms, you’ll create a SCEP certificate profile for Android, and another for iOS.

### <a name="general-considerations-when-you-use-a-microsoft-certification-authority"></a>General considerations when you use a Microsoft Certification Authority

When you use a Microsoft Certification Authority (CA):

- To use SCEP certificate profiles, you must [set up a Network Device Enrollment Service (NDES) server](certificates-scep-configure.md#set-up-ndes) for use with Intune.
- To use the following certificate profile types, you must [install the Microsoft Intune Certificate Connector](certificates-scep-configure.md#install-the-intune-certificate-connector):
  - SCEP certification profile
  - PKCS certificate profile

- To use PKCS imported certificates:
  - [Install the PFX Certificate Connector for Microsoft Intune](certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).
  - Export certificates from the certification authority and then import them to Microsoft Intune. See [the PFXImport PowerShell project](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

- Deploy certificates by using the following mechanisms:
  - [Trusted certificate profiles](certificates-configure.md#create-trusted-certificate-profiles) to deploy the Trusted Root CA certificate from your root or intermediate (issuing) CA to devices
  - SCEP sertifika profilleri
  - PKCS sertifika profilleri
  - PKCS imported certificate profiles

### <a name="general-considerations-when-you-use-a-third-party-certification-authority"></a>General considerations when you use a third-party Certification Authority

When you use a third-party (non-Microsoft) Certification Authority (CA):

- To use SCEP certificate profiles:
  - Set up integration with a third-party CA from [one of our supported partners](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners). Set up includes following the instructions from the third-party CA to complete integration of their CA with Intune.
  - [Create an application in Azure AD](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration) that delegates rights to Intune to do SCEP certificate challenge validation.

- PKCS imported certificates require you to [install the PFX Certificate Connector for Microsoft Intune](certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).

- Deploy certificates by using the following mechanisms:
  - [Trusted certificate profiles](certificates-configure.md#create-trusted-certificate-profiles) to deploy the Trusted Root CA certificate from your root or intermediate (issuing) CA to devices
  - SCEP sertifika profilleri
  - PKCS certificate profiles *(only supported with the [Digicert PKI Platform](certificates-digicert-configure.md))*
  - PKCS imported certificate profiles

## <a name="supported-platforms-and-certificate-profiles"></a>Supported platforms and certificate profiles

| Platfveyam              | Trusted certificate profile | PKCS certificate profile | SCEP certificate profile | PKCS imported certificate profile  |
|--|--|--|--|---|
| Android device administrator | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png)|  ![Desteklenir](./media/certificates-configure/green-check.png) |
| Android Kurumsal <br> - Fully Managed (Device Owner)   | ![Desteklenir](./media/certificates-configure/green-check.png) |   | ![Desteklenir](./media/certificates-configure/green-check.png) |   |
| Android Kurumsal <br> - Dedicated (Device Owner)   | ![Desteklenir](./media/certificates-configure/green-check.png)  |   | ![Desteklenir](./media/certificates-configure/green-check.png)  |   |
| Android Kurumsal <br> - Work Profile    | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) |
| iOS                   | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) |
| Mac OS                 | ![Desteklenir](./media/certificates-configure/green-check.png) |  ![Desteklenir](./media/certificates-configure/green-check.png) |![Desteklenir](./media/certificates-configure/green-check.png)|![Desteklenir](./media/certificates-configure/green-check.png)|
| WVPN profillerinidows Phone 8.1     |![Desteklenir](./media/certificates-configure/green-check.png)  |  | ![Desteklenir](./media/certificates-configure/green-check.png)| ![Desteklenir](./media/certificates-configure/green-check.png) |
| Windows 8.1 ve üzeri |![Desteklenir](./media/certificates-configure/green-check.png)  |  |![Desteklenir](./media/certificates-configure/green-check.png) |   |
| Windows 10 ve üzeri  | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) | ![Desteklenir](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Export the trusted root CA certificate

To use PKCS,  SCEP, and PKCS imported certificates, devices must trust your root Certification Authority. To establish trust, export the Trusted Root CA certificate, and any intermediate or issuing Certification Authority certificates, as a public certificate (.cer). You can get these certificates from the issuing CA, or from any device that trusts your issuing CA.

To export the certificate, refer to the documentation for your Certification Authority. You’ll need to export the public certificate as a .cer file.  Don't export the private key, a .pfx file.

You’ll use this .cer file when you [create trusted certificate profiles](#create-trusted-certificate-profiles) to deploy that certificate to your devices.

## <a name="create-trusted-certificate-profiles"></a>Create trusted certificate profiles

Create a trusted certificate profile before you can create a SCEP, PKCS, or PKCS imported certificate profile. Deploying a trusted certificate profile ensures each device recognizes the legitimacy of your CA. SCEP certificate profiles directly reference a trusted certificate profile. PKCS certificate profiles don’t directly reference the trusted certificate profile but do directly reference the server that hosts your CA. PKCS imported certificate profiles don't directly reference the trusted certificate profile but can use it on the device. Deploying a trusted certificate profile to devices ensures this trust is established. When a device doesn’t trust the root CA, the SCEP or PKCS certificate profile policy will fail.

Create a separate trusted certificate profile for each device platform you want to support, just as you'll do for SCEP, PKCS, and PKCS imported certificate profiles.

### <a name="to-create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturmak için

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Devices** > **Configuration profiles** > **Create profile**.

   ![Navigate to Intune and create a new profile for a trusted certificate](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Aşağıdaki özellikleri girin:

   - Profil için **Ad**
   - Optionally set a **Description**
   - Profili dağıtmak için **Platform**
   - **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

4. Select **Settings**, and then browse to the trusted root CA certificate .cer file you exported for use with this certificate profile, and then select **OK**.

5. Yalnızca Windows 8.1 ve Windows 10 cihazları için, güvenilen sertifika için **Hedef Depo** olarak şunlardan birini seçin:

   - **Bilgisayar sertifika deposu - Kök**
   - **Bilgisayar sertifika deposu - Ara**
   - **Kullanıcı sertifika deposu - Ara**

6. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** bölmesine gidin ve **Oluştur**’u seçin.

The profile appears in the list of profiles on the *Devices - Configuration profiles* window, with a profile type of **Trusted certificate**. Be sure to assign this profile to devices that will use SCEP or PKCS certificates. To assign the profile to groups, see [assign device profiles](../configuration/device-profile-assign.md).

> [!NOTE]
> Android devices might display a message that a third party has installed a trusted certificate.

## <a name="additional-resources"></a>Ek kaynaklar

- [Cihaz profillerini atama](../configuration/device-profile-assign.md)  
- [E-postaları imzalamak ve şifrelemek için S/MIME kullanma](certificates-s-mime-encryption-sign.md)  
- [Use third-party certification authority](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Sonraki adımlar

Create SCEP, PKCS, or PKCS imported certificate profiles for each platform you want to use. To continue, see the following articles:

- [Configure infrastructure to support SCEP certificates with Intune](certificates-scep-configure.md)  
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)  
- [Create a PKCS imported certificate profile](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)
