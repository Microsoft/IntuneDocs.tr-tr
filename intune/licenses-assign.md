---
title: Microsoft Intune lisansları atama
description: Intune’a kaydolabilmeleri için kullanıcılara lisans atama
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd8b35fbbff89ca7f4c259e1903f4c9f9a6e3b38
ms.sourcegitcommit: d2989b9992d10d133573d9bc31479659fb7e242c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71238369"
---
# <a name="assign-licenses-to-users-so-they-can-enroll-devices-in-intune"></a>Cihazlarını Intune’a kaydedebilmeleri için kullanıcılara lisans atama

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

El ile kullanıcı eklediğinizde veya şirket içi Active Directory'nizden eşitlediğinizde, kullanıcıların cihazlarını Intune'a kaydedebilmesi için önce her kullanıcıya bir Intune lisansı atamanız gerekir. Lisans listesi için bkz. [Intune barındıran lisanslar](licenses.md).

## <a name="assign-an-intune-license-in-the-microsoft-365-admin-center"></a>Microsoft 365 Yönetim merkezinde bir Intune lisansı atama

Bulut tabanlı kullanıcıları el ile eklemek ve hem bulut tabanlı kullanıcı hesaplarına hem de şirket içi Active Directory Azure AD 'ye eşitlenen hesaplara lisans atamak için [Microsoft 365 Yönetim merkezini](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanabilirsiniz.

1. [Microsoft 365 Yönetim merkezinde](http://go.microsoft.com/fwlink/p/?LinkId=698854) kiracı yöneticisi kimlik bilgilerinizi kullanarak oturum açın ve ardından **Kullanıcılar** > **etkin kullanıcılar**' ı seçin.

2. Intune kullanıcı lisansı atamak istediğiniz kullanıcı hesabını seçin ve **Ürün lisansları** > **Düzenle**’yi seçin.

3. **Intune** veya **Enterprise Mobility + Security**’i **Açık** konuma getirin ve **Kaydet**’i seçin.

   ![Microsoft 365 Yönetim Merkezi ürün lisansları bölümünün ekran görüntüsü.](./media/office-assign-license.png)

4. Kullanıcı hesabı artık hizmeti kullanmak ve yönetime cihaz kaydetmek için gereken izinlere sahiptir.

> [!NOTE]
> Kullanıcılar, klasik Intune portalında yalnızca Intune bılgısayar istemcisini kullanarak bir cihazı kaydettikten sonra görüntülenir. Ayrıca, seçili tüm kullanıcılar için lisans ekleme veya değiştirmeyi seçerek bir grup kullanıcıyı aynı anda düzenlemek üzere seçebilirsiniz.

## <a name="assign-an-intune-license-by-using-azure-active-directory"></a>Azure Active Directory kullanarak bir Intune lisansı atama

Azure Active Directory kullanarak da kullanıcılara Intune lisansları atayabilirsiniz. Daha fazla bilgi için bkz. [Azure Active Directory makalesinde kullanıcılara lisans verme](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal). 

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Eğitim için Intune kullanıcılarına lisans atamak için School Data Sync özelliğini kullanma
Bir eğitim kuruluşuysanız, eşitlenen kullanıcılara Eğitim için Intune lisansları atamak için School Data Sync (SDS) kullanabilirsiniz. SDS profilinizi ayarlarken Eğitim için Intune onay kutusunu işaretlemeniz yeterlidir.  

![SDS profil ayarının ekran görüntüsü](./media/i4e-sds-profile-setup-setting.png)

Eğitim için Intune lisansı atadığınızda, Intune A Direct lisansının da atandığından emin olun.

![Ürün lisansı ayarının ekran görüntüsü](./media/i4e-set-licenses.png)

SDS hakkında daha fazla bilgi edinmek için bkz. [School Data Sync’e genel bakış](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>Kullanıcı ve cihaz lisansları hizmetlere erişimi nasıl etkiler?
* Bir kullanıcı yazılım lisansı atadığınız her bir **Kullanıcı** , uygulamaları yönetmek için çevrimiçi hizmetler ve ilgili yazılımlara (System Center yazılımı dahil olmak üzere) erişebilir ve kullanabilir ve en fazla 15 MDM cihazı kullanabilir. Intune bılgısayar Aracısı kullanıcı lisansı başına 5 fiziksel ve 1 sanal makineye izin verir.
* Kullanıcı lisanslarından ayrı olarak her cihaz için lisans satın alabilirsiniz. Cihaz lisanslarının cihazlara atanması gerekmez. Çevrimiçi hizmetlere ve ilgili yazılımlara (System Center yazılımı da dahil) erişen ve bunları kullanan her cihazın bir cihaz lisansı olmalıdır.
* Bir cihaz birden fazla kullanıcı tarafından kullanılıyorsa, her biri için cihaz yazılım lisansı gerekir veya tüm kullanıcıların bir kullanıcı yazılım lisansı kullanması gerekir.

## <a name="understanding-the-type-of-licenses-you-have-purchased"></a>Satın aldığınız lisans türünü anlama

Intune’u satın alma şekliniz, abonelik bilgilerinizi belirleyen etkendir:

- Intune hizmetini bir Kurumsal Anlaşma yoluyla satın aldıysanız abonelik bilgilerinizi **Abonelikler** altındaki Toplu Lisans portalında bulabilirsiniz.
- Intune hizmetini bir Bulut Çözümü Sağlayıcısı yoluyla satın aldıysanız kurumsal bayinizle iletişime geçin.
- Intune hizmetini bir CC# veya Fatura ile satın aldıysanız, lisanslarınız kullanıcı temelli olacaktır.




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
