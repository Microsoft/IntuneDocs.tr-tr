---
title: "Barındırılan Exchange için Microsoft Intune Exchange bağlayıcısını yapılandırma | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6951ccdb0e37489217ef939f0cbf6fc1133a6d3c
ms.openlocfilehash: 6cfc532cba2f53034c4c3ef0c2df3d6c1e6e7841


---

# Exchange Online için Intune hizmetten hizmete bağlayıcısını yapılandırma

Microsoft Intune’la Office 365 tarafından barındırılan Exchange Online hizmeti arasında bağlantı kurmak için bu bilgileri kullanın.

## Hizmetten hizmete bağlayıcının gereksinimleri
**Hizmetten Hizmete Bağlayıcı** yalnızca barındırılan Exchange'i destekler ve şirket içi altyapıyla ilgili bir gereksinimi yoktur.

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Barındırılan Exchange yapılandırılmış ve çalışıyor|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Mobil cihaz yönetimi yetkilisi| [Mobil cihaz yönetimi yetkilisi olarak Microsoft Intune’u ayarlama](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Microsoft Exchange sürümü|Exchange Server 2013 veya üzeri bir kiracıya sahip bir Office 365 aboneliğinizin olmalıdır. Kiracı Exchange Server 2013 veya üzeri olduğu sürece, bağlayıcı aynı ortamda Exchange Server 2010'u destekler.|
|Active Directory Eşitlemesi|Intune Bağlayıcısı’nı kullanabilmeniz için, önce [Active Directory eşitlemesini ayarlamalısınız](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3). Böylelikle yerel kullanıcılarınız ve güvenlik gruplarınız Azure Active Directory örneğinizle eşitlenir.|

### Exchange cmdlet gereksinimleri

Intune Exchange Bağlayıcı tarafından kullanılan bir Exchange Online kullanıcı hesabı da oluşturmanız gerekir. Hesabın Intune yönetim konsolunu kullanma ve bu gerekli Windows PowerShell Exchange cmdlet’lerini çalıştırma izni olmalıdır:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Hizmetten hizmete bağlayıcıyı ayarlama

1. [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com), [yukarıdaki](#exchange-cmdlet-requirements) cmdlet’ler için Exchange yönetici hakları ve izinlerine sahip bir kullanıcı hesabıyla açın. Microsoft Intune, bağlantıyı ayarlamak için şu anda oturum açmış durumda olan kullanıcının e-posta adresini kullanır.

2.  Çalışma alanı kısayol bölmesinde **YÖNETİCİ**’yi seçin ve sonra **Mobil Cihaz Yönetimi** > **Microsoft Exchange** > **Exchange Bağlantısını Ayarla**’ya gidin.
![Hizmetten hizmete bağlayıcıyı ayarlama sayfası](../media/intunesa5cservicetoserviceconnector.png)

3.  **Exchange Bağlantısını Ayarla** sayfasında, **Hizmet Bağlayıcısı'nı Ayarla**'ya tıklayın.


Hizmetten Hizmete Bağlayıcısı otomatik olarak yapılandırılır ve Barındırılan Exchange ortamınızla eşitlenir.

## Exchange bağlantınızı doğrulama

Exchange Bağlayıcısı’nı başarıyla yapılandırdıktan sonra, Intune yönetim konsolunda **YÖNETİCİ** çalışma alanını seçin, **Mobile Cihaz Yönetimi** > **Microsoft Exchange**’e gidin, sonra da sizin sağladığınız ve **Exchange Bağlayıcısı Bilgileri** altında gösterilen ayrıntıları doğrulayın.

Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.



<!--HONumber=Jun16_HO4-->


