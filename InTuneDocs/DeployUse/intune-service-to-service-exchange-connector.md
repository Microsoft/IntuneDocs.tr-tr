---
title: "Exchange Online için Exchange bağlayıcısı | Microsoft Intune"
description: "Exchange ActiveSync mobil cihaz yönetimini (MDM) desteklemek için Intune’u Office 365 Exchange hizmetine bağlayın."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: de3296e81c88b3ac04e3ba3f3d3ca222a59df7bd
ms.openlocfilehash: 1aabf820170483eacc83bec5e2b275e84dc07ffd


---

# Exchange Online için Intune hizmetten hizmete bağlayıcısını yapılandırma

Microsoft Intune ile Exchange Online veya yeni Exchange Online Dedicated hizmeti arasında bağlantı kurmak için bu bilgileri kullanın. Exchange Online Dedicated ortamınızın **yeni** mi yoksa **eski** mi olduğunu belirlemek için hesap yöneticinize başvurun. Intune, abonelik başına herhangi bir türde tek bir Exchange bağlayıcısı bağlantısını destekler.

## Hizmetten hizmete bağlayıcının gereksinimleri
**Hizmetten Hizmete Bağlayıcı** yalnızca Exchange Online’ı veya yeni Exchange Online Dedicated hizmetini destekler ve şirket içi altyapıyla ilgili bir gereksinimi yoktur.

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Exchange Online yapılandırılmış ve çalışıyor|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Mobil cihaz yönetimi yetkilisi| [Mobil cihaz yönetimi yetkilisi olarak Microsoft Intune’u ayarlama](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Microsoft Exchange sürümü|Exchange Online veya yeni Exchange Online Dedicated hizmeti|
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


Hizmetten Hizmete Bağlayıcı otomatik olarak yapılandırılır ve Exchange Online veya yeni Exchange Online Dedicated ortamınızla eşitlenir.

## Exchange bağlantınızı doğrulama

Exchange Bağlayıcısı’nı başarıyla yapılandırdıktan sonra, [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetici**’yi seçin, **Mobile Cihaz Yönetimi** > **Microsoft Exchange**’e gidin, sonra da sizin sağladığınız ve **Exchange Bağlayıcısı Bilgileri** altında gösterilen ayrıntıları doğrulayın.

Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.



<!--HONumber=Jul16_HO5-->


