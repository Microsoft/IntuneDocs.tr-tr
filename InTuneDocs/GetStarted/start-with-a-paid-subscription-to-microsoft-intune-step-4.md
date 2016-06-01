---
# required metadata

title: Intune lisanslarını yönetme | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune lisanslarını yönetme
Kullanıcının hizmette oturum açabilmek veya cihazlarını yönetime kaydedebilmek için Intune aboneliğinizde bir lisansı olması gerekir. Kullanıcıların bir lisansı olduğunda, [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] kullanıcı grubunun üyesi olurlar. Bu grup, aboneliği kullanmak için bir lisansı olan tüm kullanıcıları içerir. Her kullanıcı lisansı 5 cihaza kadar kaydetmeyi destekler.

## Intune lisansları nasıl atanır
Kullanıcı hesaplarınız şirket için Active Directory’nizden eşitlendiğinde veya hesap portalı aracılığıyla bulut hizmetleri aboneliğinize el ile eklendiğinde, bunlara otomatik olarak Intune lisansı atanmaz. Bunun yerine, daha sonra bir Intune kiracı yöneticisinin kullanıcı hesabını düzenleyerek hesap portalından kullanıcıya lisans ataması gerekir.

Aboneliğiniz Azure AD'yi aboneliğinizle ilişkilendirilmiş diğer bulut hizmetleriyle paylaştığında, bu hizmetlere eklenen kullanıcılara da erişiminiz olur. Bu kullanıcıların siz onlara bir lisans atayana kadar [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansı olmaz.

> [!TIP]
> [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansı atama veya geri alma seçeneği devre dışı bırakıldıysa, aboneliğiniz [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx) kullanırken mevcut olan seçenekler gibi toplu lisanslama seçenekleri içeriyor olabilir. Lisans atama veya geri alma hakkında bilgi almak için lisanslama seçeneklerinizin belgelerine bakın.

## Intune kullanıcı lisansı atama

Bulut tabanlı kullanıcıları el ile eklemek ve hem bulut tabanlı kullanıcı hesaplarına hem de şirket için Active Directory’nizden Azure AD’ye eşitlenen hesaplara lisans atamak için **[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]** kullanırsınız.

1.  Kiracı yöneticisi kimlik bilgilerinizi kullanarak Intune hesap portalında oturum açın.

2.  Intune kullanıcı lisansı atamak istediğiniz kullanıcı hesabını seçin ve kullanıcı hesabı özelliklerinde **Microsoft Intune** onay kutusunu etkinleştirin.

3.  Kullanıcı hesabı artık Microsoft Intune kullanıcı grubuna eklenir. Bu grup kullanıcıya hizmeti kullanmak ve cihazlarını yönetime kaydetmek için izinler verir.

### EMS kullanıcı lisanslarını seçmeli yönetmek için PowerShell kullanma
Microsoft'un Enterprise Mobility Suite (EMS) ürününü kullanan kuruluşların, EMS paketinden yalnızca Azure Active Directory Premium veya Intune hizmetlerine ihtiyacı olan kullanıcıları olabilir. [Azure Active Directory PowerShell cmdlet’lerini](https://msdn.microsoft.com/library/jj151815.aspx) kullanarak, hizmetlerin birini veya bir alt kümesini atayabilirsiniz. 

EMS hizmetlerinin kullanıcı lisanslarını seçmeli atamak için, [Windows PowerShell için Azure Active Directory Modülü](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule)’nün yüklü olduğu bilgisayarda bir yönetici olarak PowerShell’i açın. PowerShell’i yerel bilgisayara veya ADFS sunucusuna yükleyebilirsiniz.

Yalnızca istenen hizmet planları için geçerli olan yeni bir lisans SKU tanımı oluşturmalısınız. Bunu yapmak için, uygulamak istemediğiniz planları devre dışı bırakın. Örneğin, Intune lisansı atamayan bir lisans SKU tanımı oluşturabilirsiniz. Kullanılabilen hizmetlerin listesini görmek için şunu yazın:
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Intune hizmet planını hariç tutmak için aşağıdaki komutu çalıştırabilirsiniz. Güvenlik grubunun tamamına yayılmak için aynı yöntemi kullanabileceğiniz gibi, daha ayrıntılı filtreler de kullanabilirsiniz. 

Örnek 1

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Komut satırında yeni kullanıcı oluşturun ve lisansın Intune bölümünü etkinleştirmeden bir EMS lisansı atayın:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

Şununla doğrulayın:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Örnek 2
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![Zaten lisans atanmış bir kullanıcı için EMS lisansının Intune bölümünü devre dışı bırakın:](./media/posh-addlic-verify.png)

### Şununla doğrulayın:
PoSH-AddLic-Verify Sonraki adımlar
>Tebrikler!

>*Intune hızlı başlangıç kılavuzunun* 4. adımını tamamlamış oldunuz.  


<!--HONumber=May16_HO2-->


