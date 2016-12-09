---
title: "Intune lisanslarını yönetme | Microsoft Intune"
description: "Intune aboneliğiniz için kullanıcılara lisans atama"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: f0f9d60a27afa580aaba8a3c24fff6325ae53f08


---

# <a name="manage-intune-licenses"></a>Intune lisanslarını yönetme
Kullanıcıların Intune hizmetini kullanmak veya cihazlarını yönetime kaydetmek üzere oturum açabilmesi için önce [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854) aracılığıyla her kullanıcıya Intune aboneliğinize yönelik bir lisans atamanız gerekir.

Microsoft Enterprise Mobility + Security (EMS) kullanan kuruluşların, yalnızca EMS paketinde Azure Active Directory Premium veya Intune hizmetleri gerektiren kullanıcıları olabilir. [Azure Active Directory PowerShell cmdlet’lerini](https://msdn.microsoft.com/library/jj151815.aspx) kullanarak hizmetlerin birini veya bir alt kümesini atayabilirsiniz. Daha fazla bilgi için bkz. [Intune lisanslarını PowerShell kullanarak yönetme](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md).

## <a name="how-intune-licenses-are-assigned"></a>Intune lisansları nasıl atanır
Kullanıcı hesapları şirket içi Active Directory’nizden eşitlendiğinde veya [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854) aracılığıyla el ile bulut hizmetleri aboneliğinize eklendiğinde, bu hesaplara otomatik olarak bir Intune lisansı atanmaz. Bunun yerine, daha sonra bir Intune kiracı yöneticisinin kullanıcı hesabını düzenleyerek Office 365 portalından kullanıcıya lisans ataması gerekir.

Aboneliğiniz Azure AD'yi aboneliğinizle ilişkilendirilmiş diğer bulut hizmetleriyle paylaştığında, bu hizmetlere eklenen kullanıcılara da erişiminiz olur. Bu kullanıcıların siz onlara bir lisans atayana kadar [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansı olmaz.

> [!TIP]
> [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansı atama veya geri alma seçeneği devre dışı bırakıldıysa, aboneliğiniz [Enterprise Mobility Suite + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx) kullanırken mevcut olan seçenekler gibi toplu lisanslama seçenekleri içeriyor olabilir. Lisans atama veya geri alma hakkında bilgi almak için lisanslama seçeneklerinizin belgelerine bakın.

## <a name="assign-an-intune-user-license"></a>Intune kullanıcı lisansı atama

Bulut tabanlı kullanıcılar eklemek ve hem bulut tabanlı kullanıcı hesaplarına hem de şirket içi Active Directory’nizden Azure AD’ye eşitlenen hesaplara lisans atamak için [Office 365 portalını](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanabilirsiniz.

1.  [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) kiracı yöneticisi kimlik bilgilerinizi kullanarak oturum açın, sonra **Kişiler** > **Tüm Kullanıcılar**’ı seçin.

2.  Intune kullanıcı lisansı atamak istediğiniz kullanıcı hesabını ve sonra **Microsoft Intune**’u veya **Enterprise Mobility Suite**’i seçin.

3.  Kullanıcı hesabı artık hizmeti kullanmak ve yönetime cihaz kaydetmek için gereken izinlere sahiptir.

> [!NOTE]
> Kullanıcılar, cihazlarını kaydettikten sonra konsolda görünür.

### <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>EMS kullanıcı lisanslarını seçmeli yönetmek için PowerShell kullanma
Microsoft Enterprise Mobility + Security (eskiden Enterprise Mobility Suite) kullanan kuruluşların, yalnızca EMS paketinde Azure Active Directory Premium veya Intune hizmetleri gerektiren kullanıcıları olabilir. [Azure Active Directory PowerShell cmdlet’lerini](https://msdn.microsoft.com/library/jj151815.aspx) kullanarak hizmetlerin birini veya bir alt kümesini atayabilirsiniz.

EMS hizmetlerinin kullanıcı lisanslarını seçmeli atamak için, [Windows PowerShell için Azure Active Directory Modülü](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule)’nün yüklü olduğu bilgisayarda bir yönetici olarak PowerShell’i açın. PowerShell’i yerel bilgisayara veya ADFS sunucusuna yükleyebilirsiniz.

Yalnızca istenen hizmet planları için geçerli olan yeni bir lisans SKU tanımı oluşturmalısınız. Bunu yapmak için, uygulamak istemediğiniz planları devre dışı bırakın. Örneğin, Intune lisansı atamayan bir lisans SKU tanımı oluşturabilirsiniz. Kullanılabilen hizmetlerin listesini görmek için şunu yazın:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Intune hizmet planını hariç tutmak için aşağıdaki komutu çalıştırabilirsiniz. Güvenlik grubunun tamamına yayılmak için aynı yöntemi kullanabileceğiniz gibi, daha ayrıntılı filtreler de kullanabilirsiniz.

**Örnek 1**<br>
Komut satırında yeni kullanıcı oluşturun ve lisansın Intune bölümünü etkinleştirmeden bir EMS lisansı atayın:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Şununla doğrulayın:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Örnek 2**<br>
Zaten lisans atanmış bir kullanıcı için EMS lisansının Intune bölümünü devre dışı bırakın:

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

Şununla doğrulayın:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

>[!div class="step-by-step"]

>[&larr;**Kullanıcıları Intune ile eşitleme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md) [**Kullanıcıları ve cihazları düzenleme**&rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  



<!--HONumber=Dec16_HO2-->


