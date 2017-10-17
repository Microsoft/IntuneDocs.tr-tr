---
title: "Uygulama başına VPN için bir paket aile adı (PFN) bulma"
description: "Uygulama başına VPN’yi yapılandırabilmek için bir PFN bulun."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 884aa820a6511c96269dde88b408674a21fb9dd4
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a>Uygulama başına VPN yapılandırması için paket aile adı (PFN) bulma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Uygulama başına VPN’yi ayarlamak için bir PFN bulmanın iki yolu vardır.

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a>Windows 10 bilgisayarında yüklü bir uygulama için PFN bulma

Üzerinde çalıştığınız uygulama zaten bir Windows 10 bilgisayarında yüklüyse, PFN’yi almak için [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) PowerShell cmdlet’ini kullanabilirsiniz.

Get-AppxPackage cmdlet’inin söz dizimi:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
PFN’yi alabilmek için PowerShell’i yönetici olarak çalıştırmanız gerekebilir.

Örneğin, bilgisayarda yüklü tüm evrensel uygulamalar hakkındaki bilgileri almak için `Get-AppxPackage` kullanın.

Adının tamamını veya bir kısmını bildiğiniz bir uygulama hakkındaki bilgileri almak için `Get-AppxPackage *<app_name>` kullanın. Uygulamanın tam adını bilmediğiniz durumlarda joker karakter kullanmanın özellikle çok yararlı olduğunu aklınızda bulundurun. Örneğin, OneNote’la ilgili bilgi almak için `Get-AppxPackage *OneNote` kullanın.


OneNote için şu bilgiler alınır:

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a>Uygulama bilgisayarda yüklü olmadığında bir PFN bulma

1.  https://www.microsoft.com/store/apps adresine gidin.
2.  Arama çubuğuna uygulamanın adını girin. Bizim örneğimizde, OneNote için arama yapın.
3.  Uygulamanın bağlantısını seçin. URL’nin sonunda bir dizi harf olduğuna dikkat edin. Bizim örneğimizde, URL şöyle görünür: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.
4.  Farklı bir sekmede, şu URL’yi yapıştırın: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. `<app id>` bölümünü, https://www.microsoft.com/store/apps adresinden aldığınız uygulama kimliğiyle değiştirin (3. adımdaki URL’nin sonunda yer alan harf serisi). Bizim OneNote örneğimizde, şunu yapıştırırsınız: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

Microsoft Edge istediğiniz bilgileri görüntüler; Internet Explorer’da bilgileri görmek için **Aç**’ı seçin. PFN değeri ilk satırda verilir. İşte bizim örneğimizin sonuçları:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
