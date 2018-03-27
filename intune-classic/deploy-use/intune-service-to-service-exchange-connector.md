---
title: Exchange Online için Exchange Connector
description: Exchange ActiveSync mobil cihaz yönetimini (MDM) desteklemek için Intune’u Office 365 Exchange hizmetine bağlayın.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 78b4e91fd61bb79c2a3a6d86d5a79c39b320cc5e
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Exchange Online için Intune hizmetten hizmete bağlayıcısını yapılandırma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune ile Exchange Online veya yeni Exchange Online Dedicated hizmeti arasında bağlantı kurmak için bu bilgileri kullanın. Exchange Online Dedicated ortamınızın **yeni** veya **eski** sürüm mü olduğunu belirlemek için hesap yöneticinize başvurun. Intune, abonelik başına herhangi bir türde tek bir Exchange bağlayıcısı bağlantısını destekler.

## <a name="service-to-service-connector-requirements"></a>Hizmetten Hizmete Bağlayıcı gereksinimleri
**Hizmetten Hizmete Bağlayıcı** yalnızca Exchange Online veya Exchange Online Dedicated hizmetini destekler ve şirket içi altyapıyla ilgili bir gereksinimi yoktur.

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Exchange Online yapılandırılmış ve çalışıyor|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Mobil cihaz yönetimi yetkilisi| [Mobil cihaz yönetimi yetkilisi olarak Microsoft Intune’u ayarlama](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Microsoft Exchange sürümü|Exchange Online veya yeni Exchange Online Dedicated hizmeti|/intune/users-permissions-add
|Active Directory eşitlemesi|Intune Bağlayıcısı’nı kullanabilmeniz için, önce [Active Directory eşitlemesini ayarlamalısınız](/intune/users-permissions-add). Böylelikle yerel kullanıcılarınız ve güvenlik gruplarınız Azure Active Directory örneğinizle eşitlenir.|

### <a name="exchange-cmdlet-requirements"></a>Exchange cmdlet gereksinimleri

Intune Exchange Bağlayıcı tarafından kullanılan bir Exchange Online kullanıcı hesabı da oluşturmanız gerekir. Hesabın Intune yönetim konsolunu kullanma ve aşağıdaki gerekli Windows PowerShell Exchange cmdlet’lerini çalıştırma izni olmalıdır:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Hizmet Bağlayıcısı'nı ayarlama

1. [Microsoft Intune yönetim konsolunu](https://manage.microsoft.com), [daha önce açıklanan](#exchange-cmdlet-requirements) cmdlet’ler için Exchange yönetici hak ve izinlerine sahip bir kullanıcı hesabıyla açın. Microsoft Intune, bağlantıyı ayarlamak için o anda giriş yapmış olan kullanıcının e-posta adresini kullanır.

2.  Çalışma alanı kısayolları bölmesinde, **YÖNETİCİ**>**Mobil Cihaz Yönetimi** > **Microsoft Exchange** > **Exchange Bağlantısını Ayarla**'yı seçin.
![Hizmetten hizmete bağlayıcı ayarlama sayfası](../media/intunesa5cservicetoserviceconnector.png)

3.  **Exchange Bağlantısını Ayarla** sayfasında, **Hizmet Bağlayıcısı'nı Ayarla**'ya tıklayın.


Hizmetten Hizmete Bağlayıcı, Exchange Online veya yeni Exchange Online Dedicated ortamınızı otomatik olarak yapılandırır ve eşitler.

## <a name="validate-your-exchange-connection"></a>Exchange bağlantınızı doğrulama

Exchange Bağlayıcısını başarıyla yapılandırdıktan sonra [Microsoft Intune yönetim konsoluna](https://manage.microsoft.com) gidin. **Yönetici**> **Mobil Cihaz Yönetimi** > **Microsoft Exchange**'i seçin. Ardından, verdiğiniz ayrıntıların **Exchange Bağlantı Bilgileri** altında göründüğünü doğrulayın.

Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.
