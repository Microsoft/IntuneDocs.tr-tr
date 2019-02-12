---
title: Exchange Online için Intune Exchange connector | Microsoft Intune
description: Exchange ActiveSync mobil cihaz yönetimini (MDM) desteklemek için Intune’u Office 365 Exchange hizmetine bağlayın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2706a12f9f4844f96d279f753e7cd99f159ca856
ms.sourcegitcommit: e262b0ad8df610e25eb9421b9ebc2673bcf1020e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2019
ms.locfileid: "55986816"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Intune ve Exchange Online için Exchange hizmet bağlayıcısını yapılandırma
Bu makale, Microsoft Intune hizmetini Exchange Online veya yeni Exchange Online Dedicated hizmetine nasıl bağlayacağınızı gösterir. Exchange Online Dedicated ortamınızın **yeni** veya **eski** sürüm mü olduğunu belirlemek için hesap yöneticinize başvurun.

**Hizmetten Hizmete Bağlayıcı** ile hem Exchange ActiveSync’i (EAS) hem de Intune tarafından yönetilen cihazları tek bir yönetim konsolundan yönetebilirsiniz.  Exchange Online için Koşullu Erişimi etkinleştirmek için bağlayıcı gerekli değildir.

Koşullu erişim bir dağıtımı planlarken, genellikle hangi kullanıcıların ve kullanıcı sayısı, yeni deneyimi sunacak anlamak önemlidir. Office 365 Yönetim Merkezi bu portal, etkinlik raporları özelliğinin bir parçası olarak Exchange Online bir e-posta uygulama kullanım raporu biçiminde sağlar. Bu raporlar, ortamınızdaki mobil e-posta benimseme önce ve sonra koşullu erişim dağıtımını anlamak için kullanılabilir.

## <a name="service-to-service-connector-requirements"></a>Hizmetten Hizmete Bağlayıcı gereksinimleri
**Hizmetten Hizmete Bağlayıcı**, yalnızca Exchange Online veya Exchange Online Dedicated hizmetini destekler ve şirket içi altyapıyla ilgili bir gereksinimi yoktur. 


|              Gereksinim               |                                                                                                            Daha fazla bilgi                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exchange Online yapılandırılmış ve çalışıyor |                                                                                 [Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Mobil cihaz yönetimi yetkilisi   |                                                       [Mobil cihaz yönetimi yetkilisi olarak Microsoft Intune’u ayarlama](mdm-authority-set.md)                                                       |
|       Microsoft Exchange sürümü       |                                                                                      Exchange Online veya yeni Exchange Online Dedicated hizmeti                                                                                      |
|    Active Directory eşitlemesi    | Intune Bağlayıcısı’nı kullanabilmeniz için, önce [Active Directory eşitlemesini ayarlamalısınız](/intune/users-add). Böylelikle yerel kullanıcılarınız ve güvenlik gruplarınız Azure Active Directory örneğinizle eşitlenir. |

### <a name="exchange-cmdlet-requirements"></a>Exchange cmdlet gereksinimleri

Intune Exchange hizmet bağlayıcısı tarafından kullanılan bir Exchange Online kullanıcı hesabı da oluşturmanız gerekir. Hesabın aşağıdaki gerekli Windows PowerShell Exchange cmdlet'lerini çalıştırma izni olması gerekir:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Hizmet Bağlayıcısı'nı ayarlama

1. [Daha önce açıklanan](#exchange-cmdlet-requirements) cmdlet’ler için Exchange yönetici hak ve izinlerine, geçerli bir Intune lisansına ve Genel Yönetici rolüne sahip bir kullanıcı hesabıyla [Azure portalında](https://portal.azure.com) oturum açın. Microsoft Intune, bağlantıyı ayarlamak için o anda giriş yapmış olan kullanıcının e-posta adresini kullanır.

2. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. Microsoft Intune panosunu açmak için **Intune**’u seçin. **Koşullu erişim**’i seçin ve daha sonra **Kurulum** altında **Exchange hizmet bağlayıcısı**’nı seçin.

4.  **Koşullu erişim - Exchange hizmet bağlayıcısı** sayfasında **Hizmetten Hizmete Bağlayıcıyı Ayarla**’yı seçin. 
   
     ![Hizmetten Hizmete Bağlayıcıyı Ayarla bağlantısını seçmeyi gösteren görüntü](media/exchange_service_connector.png)

Hizmetten Hizmete Bağlayıcı, Exchange Online veya yeni Exchange Online Dedicated ortamınızı otomatik olarak yapılandırır ve eşitler.

## <a name="validate-your-exchange-connection"></a>Exchange bağlantınızı doğrulama

Exchange Hizmetten Hizmete Bağlayıcıyı başarıyla yapılandırdıktan sonra **Koşullu erişim - Exchange hizmet bağlayıcısı** sayfasındaki Exchange Bağlayıcı Sunucusu bilgilerini doğrulayın.

**Bağlantı durumu** ile son başarılı eşitleme denemesinin tarih ve saatini de kontrol edebilirsiniz.

 
