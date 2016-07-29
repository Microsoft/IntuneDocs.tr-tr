---
title: "Uygulama başına VPN için paket aile adı (PFN) bulma | Microsoft Intune"
description: "Uygulama başına VPN’yi yapılandırabilmek için bir PFN bulun."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9a124663a80bb477d0312faa0fb43e4457ba8246
ms.openlocfilehash: 0bbb8aef7929ac09ef5f6a5a466d66b5df03e921


---

# Uygulama başına VPN yapılandırması için paket aile adı (PFN) bulma

Uygulama başına VPN’yi yapılandırabilmek için bir PFN bulmanın iki yolu vardır.

## Windows 10 bilgisayarında yüklü bir uygulama için PFN bulma

Üzerinde çalıştığınız uygulama zaten bir Windows 10 bilgisayarında yüklüyse, PFN’yi almak için [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) PowerShell cmdlet’ini kullanabilirsiniz.

Get-AppxPackage cmdlet’inin söz dizimi:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> Not: PFN’yi alabilmek için PowerShell’i yönetici olarak çalıştırmanız gerekebilir

Örneğin, bilgisayarda yüklü tüm evrensel uygulamalarla ilgili bilgileri almak için `Get-AppxPackage` kullanın.

Adının tamamını veya bir kısmını bildiğiniz uygulamayla ilgili bilgileri almak için `Get-AppxPackage *<app_name>` kullanın. Uygulamanın tam adını bilmediğiniz durumlarda joker karakter kullanmanın özellikle çok yararlı olduğunu aklınızda bulundurun. Örneğin, OneNote’la ilgili bilgi almak için `Get-AppxPackage *OneNote` kullanın.


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



## Uygulama bilgisayarda yüklü olmadığında bir PFN bulma

1.  https://www.microsoft.com/en-us/store/apps adresine gidin
2.  Arama çubuğuna uygulamanın adını girin. Bizim örneğimizde, OneNote için arama yapın.
3.  Uygulamanın bağlantısına tıklayın. Eriştiğiniz URL’nin sonunda bir dizi harf olduğuna dikkat edin. Bizim örneğimizde, URL şöyle görünür:
`https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`
4.  Başka bir sekmede, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata` URL’sini yapıştırın; `<app id>` bölümü https://www.microsoft.com/en-us/store/apps adresinden aldığınız uygulama kimliğiyle değiştirin (3. adımındaki URL’nin sonunda yer alan harf serisi). Bizim Outlook örneğimizde, şunu yapıştırırsınız: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

Edge’de istediğiniz bilgi görüntülenir; Internet Explorer’da bilgileri görmek için **Aç**’a tıklayın. PFN değeri ilk satırda verilir. Bizim örneğimizde sonuçlar şöyle görünür:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Jul16_HO4-->


