---
title: Windows bilgisayar yönetimini basitleştirmek için ilkeler kullanma
titlesuffix: Microsoft Intune
description: Microsoft Intune Center için Windows bilgisayar yönetim ilke ve ayarlarını açıklar.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: df89c2de118d3c1c299ccd662268766ec4d03d30
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57234330"
---
# <a name="use-policies-to-simplify-windows-pc-management"></a>Windows bilgisayar yönetimini basitleştirmek için ilkeler kullanma

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Windows masaüstü cihazlar üzerindeki Intune yazılım istemcisini çalıştırarak bu cihazları bilgisayar olarak yönetmek için yalnızca Intune yönetim konsolundaki **Bilgisayar Yönetimi** ilkeleri altındaki ilkeleri kullanabilirsiniz. Yönetim konsolunda listelenen tüm diğer ilkeler yalnızca mobil cihazlara yöneliktir. Microsoft Intune Center'daki ayarları yapılandırmak, bilgisayarlarda yapılan güncelleştirmeleri denetlemek ve bilgisayarlarda Windows Güvenlik Duvarı’nı yapılandırmak için **Bilgisayar Yönetimi** ilkelerini kullanın.

![Windows bilgisayarlar için ilkeler şablonu](media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a>Microsoft Intune Center’ı yönetme
Kullanıcılar Intune yazılımı istemcisini **Microsoft Intune Center** olarak görür. Microsoft Intune Center kullanıcıların şunları yapmasını sağlar:

-   Şirket portalı üzerinden uygulamaları alma.

-   Güncelleştirmeleri denetleme.

-   Microsoft Intune Endpoint Protection’ı yönetme

-  Uzaktan yardım isteyin.

Microsoft Intune Center, tüm yönetilen bilgisayarlarda yüklüdür. Intune ilkesinde aşağıdaki ayarları yapılandırabilirsiniz ve bunlar Microsoft Intune Center’da kullanıcılara gösterilir:

|İlke ayarı|Ayrıntılar|
|------------------|--------------------|
|**Ad**|Bilgisayarı yöneten yöneticinin adı.<br />En fazla uzunluk: 40 karakter|
|**Telefon numarası**|Bilgisayarı yöneten yöneticinin telefon numarası.<br />En fazla uzunluk: 20 karakter|
|**E-posta adresi**|Bilgisayarı yöneten yöneticinin e-posta adresi.<br />En fazla uzunluk: 40 karakter|
|**Web sitesinin adı**|Kullanıcılar için destek web sitenizin adı.<br />> en fazla uzunluk: 40 karakter|
|**Web sitesi URL'si**|Destek web sitenizin URL'si.<br />En fazla uzunluk: 150 karakter|
|**Notlar**|Kullanıcılara gösterilen bir not.<br />En fazla uzunluk: 120 karakter|

Windows bilgisayarlarda yapılandırabileceğiniz ilkeler ve ayarlar hakkında bilgi için aşağıdaki kaynaklara bakın:

- [Microsoft Intune’da yazılım güncelleştirmeleri ile Windows bilgisayarlarını güncel tutun](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) - Bu ilkeler, yönetilen bilgisayarların Microsoft ve üçüncü taraf yazılım güncelleştirmelerini denetlemesini ve indirmesini sağlar. Bu güncelleştirmeler, işletim sistemi yükseltmelerini (Windows 7’den Windows 10’a yükseltme veya bir Windows 10 sürümünden sonraki bir sürüme yükseltme gibi) kapsamaz.

- [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) - Bu ayarlar zamanlanmış taramaları ve kötü amaçlı yazılım algılandığında yapılacak işlemleri içerebilir.

- [Microsoft Intune’da Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) - Bu ilkeler, yönetilen bilgisayarlarda Windows Güvenlik Duvarı ayarlarını yönetmeyi kolay hale getirir.


### <a name="see-also"></a>Ayrıca bkz.

[Intune yazılım istemcisi ile genel Windows bilgisayar yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
