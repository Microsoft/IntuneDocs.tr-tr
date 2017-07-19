---
title: "Intune lisanslarını atama"
description: "Intune aboneliğiniz için kullanıcılara lisans atama"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 317fad8beb708a10a4dbf81a04f03c2faab41925
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="assign-intune-licenses-to-your-user-accounts"></a>Kullanıcı hesaplarınıza Intune lisansları atama

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

El ile kullanıcı eklediğinizde veya şirket içi Active Directory'nizden eşitlediğinizde, kullanıcıların cihazlarını Intune'a kaydedebilmesi için önce her kullanıcıya bir Intune lisansı atamanız gerekir.

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Office 365 Yönetim merkezinden bir Intune lisansı atama

Bulut tabanlı kullanıcılar eklemek ve hem bulut tabanlı kullanıcı hesaplarına hem de şirket içi Active Directory’nizden Azure AD’ye eşitlenen hesaplara lisans atamak için [Office 365 portalını](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanabilirsiniz.

1.  [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) kiracı yöneticisi kimlik bilgilerinizi kullanarak oturum açın, sonra **Kullanıcılar** > **Etkin Kullanıcılar**’ı seçin.

2.  Intune kullanıcı lisansı atamak istediğiniz kullanıcı hesabını seçin ve **Ürün lisansları** > **Düzenle**’yi seçin.

3.  **Intune** veya **Enterprise Mobility + Security**’i **Açık** konuma getirin ve **Kaydet**’i seçin.

  ![Office 365 portalı Ürün lisansı atama görüntüsü.](./media/office-assign-license.png)

4. Kullanıcı hesabı artık hizmeti kullanmak ve yönetime cihaz kaydetmek için gereken izinlere sahiptir.

> [!NOTE]
> Kullanıcılar, sadece cihazlarını kaydettikten sonra Yönetim konsolunda görünür. Ayrıca, seçili tüm kullanıcılar için lisans ekleme veya değiştirmeyi seçerek bir grup kullanıcıyı aynı anda düzenlemek üzere seçebilirsiniz.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Eğitim için Intune kullanıcılarına lisans atamak için School Data Sync özelliğini kullanma
Bir eğitim kuruluşuysanız, eşitlenen kullanıcılara Eğitim için Intune lisansları atamak için School Data Sync (SDS) kullanabilirsiniz. SDS profilinizi ayarlarken Eğitim için Intune onay kutusunu işaretlemeniz yeterlidir.  

![SDS profil ayarının görüntüsü](./media/i4e-sds-profile-setup-setting.png)

Eğitim için Intune lisansı atadığınızda, Intune A Direct lisansının da atandığından emin olun.

![Ürün lisansı ayarının görüntüsü](./media/i4e-set-licenses.png)

SDS hakkında daha fazla bilgi edinmek için bkz. [School Data Sync’e genel bakış](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US).

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>Kullanıcı ve cihaz lisansları hizmetlere erişimi nasıl etkiler?
* Bir kullanıcı yazılım lisansı atadığınız her **kullanıcı** uygulamaları yönetmek için ve 15 cihaza kadar çevrimiçi hizmetlere ve ilgili yazılımlara (System Center yazılımı dahil olmak üzere) erişebilir ve bunları kullanabilir.
* Bir cihaz yazılım lisansı atadığınız her **cihaz** herhangi bir kullanıcı sayısında kullanım için çevrimiçi hizmetlere ve ilgili yazılımlara (System Center yazılımı dahil olmak üzere) erişebilir ve bunları kullanabilir.
* Bir cihaz birden fazla kullanıcı tarafından kullanılıyorsa, her biri için cihaz yazılım lisansı gerekir veya tüm kullanıcıların bir kullanıcı yazılım lisansı kullanması gerekir.

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>EMS kullanıcı lisanslarını seçmeli yönetmek için PowerShell kullanma
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

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Şununla doğrulayın:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
